# Deployment Diagram

```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Deployment.puml

title E-commerce Platform - Deployment Diagram (AWS EKS)

Deployment_Node(aws, "AWS Cloud", "Amazon Web Services") {
    Deployment_Node(vpc, "VPC", "Virtual Private Cloud") {
        Deployment_Node(public_subnet, "Public Subnet", "10.0.1.0/24") {
            Deployment_Node(alb, "Application Load Balancer", "AWS ALB") {
                Container(load_balancer, "Load Balancer", "ALB", "Routes traffic to EKS")
            }
            Deployment_Node(nat, "NAT Gateway", "AWS NAT Gateway") {
                Container(nat_gw, "NAT Gateway", "NAT", "Outbound internet access")
            }
        }
        
        Deployment_Node(private_subnet, "Private Subnet", "10.0.2.0/24") {
            Deployment_Node(eks, "EKS Cluster", "Kubernetes 1.24") {
                Deployment_Node(node_group, "Node Group", "EC2 Instances") {
                    Container(api_gateway, "API Gateway", "Kong", "API routing and rate limiting")
                    Container(user_service, "User Service", "Node.js Pod", "User management")
                    Container(product_service, "Product Service", "Java Pod", "Product catalog")
                    Container(order_service, "Order Service", "Python Pod", "Order processing")
                }
            }
            
            Deployment_Node(rds, "RDS Subnet Group", "Database subnet") {
                ContainerDb(postgres, "PostgreSQL", "RDS PostgreSQL", "Relational data")
                ContainerDb(redis, "Redis", "ElastiCache", "Cache layer")
            }
        }
    }
}

Deployment_Node(external, "External Services") {
    System_Ext(stripe, "Stripe", "Payment processing")
    System_Ext(sendgrid, "SendGrid", "Email notifications")
}

Person(user, "End User", "Application user")

Rel(user, load_balancer, "HTTPS requests")
Rel(load_balancer, api_gateway, "Routes to")
Rel(api_gateway, user_service, "Service calls")
Rel(api_gateway, product_service, "Service calls")
Rel(api_gateway, order_service, "Service calls")

Rel(user_service, postgres, "Database queries")
Rel(product_service, redis, "Cache access")
Rel(order_service, postgres, "Database queries")

Rel(order_service, stripe, "Payment API")
Rel(user_service, sendgrid, "Email API")

@enduml
``` 