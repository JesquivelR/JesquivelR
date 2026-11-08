# Jorge Esquivel

Ingeniero DevOps en Lima, Perú. Trabajo con infraestructura en AWS escrita en Terraform, contenedores y pipelines de CI/CD. Lo que más me interesa ahora es la seguridad dentro del pipeline, por ejemplo cortar el despliegue cuando aparece un secreto en el código o una imagen con vulnerabilidades críticas. También trabajo bastante con la gestión de secretos e identidades entre el CI, Kubernetes y la nube, sobre todo con Vault.

Aquí están los proyectos y laboratorios que he construido. Los repositorios incluyen el diagrama de arquitectura y los pasos para desplegar.

## Proyectos destacados

### [Plataforma de contenedores en AWS](https://github.com/JesquivelR/plataforma-contenedores-aws)

Dos APIs en FastAPI corren en ECS Fargate detrás de un Application Load Balancer, en subredes privadas con salida por NAT Gateway. Cuando se sube una imagen nueva a ECR, EventBridge invoca una Lambda que actualiza el servicio de ECS. La infraestructura está separada en módulos de Terraform (VPC, IAM, ECS, ALB) con entornos dev y stage, y el estado remoto vive en S3. GitHub Actions construye las imágenes, las publica en ECR y aplica los cambios de infraestructura.

`Terraform` `ECS Fargate` `ALB` `Lambda` `EventBridge` `ECR` `GitHub Actions` `Docker`

### [Plataforma de datos en AWS](https://github.com/JesquivelR/plataforma-datos-aws)

Infraestructura para un data lake: buckets de S3 con cifrado, ciclo de vida y logging, un crawler de AWS Glue que cataloga los CSV, una base de datos en RDS cuya contraseña se genera y guarda en Secrets Manager, y autenticación con Cognito.

`Terraform` `S3` `AWS Glue` `RDS` `Cognito` `Secrets Manager`

## Herramientas

| Área | Herramientas |
|---|---|
| Nube | AWS (EKS, ECS Fargate, Lambda, VPC, IAM, KMS, S3, RDS PostgreSQL, MSK, Route 53, ACM, WAF, Secrets Manager, SSM), Azure (Entra ID, DNS), Cloudflare (DNS, DMARC) |
| Infraestructura como código | Terraform con módulos y estado en S3 con bloqueo nativo (`use_lockfile`), parámetros en SSM Parameter Store |
| Kubernetes | EKS y clústeres on-premise sobre RHEL, Karpenter, Helm, NGINX Ingress detrás de NLB, HPA y PDB, Argo CD |
| Identidad y secretos | HashiCorp Vault (PKI, cert auth, Kubernetes auth, JWT/OIDC, KV v2, audit log), External Secrets Operator, IRSA, SAML con Entra ID |
| CI/CD | GitHub Actions (OIDC, acciones fijadas por SHA), Jenkins, Bitbucket Pipelines con runners propios, AWS CodeBuild, AWS CodeArtifact, Dependabot |
| Seguridad en el pipeline | SonarQube, OWASP Dependency-Check, Trivy, gitleaks, Semgrep, OSV-Scanner |
| Observabilidad y carga | OpenTelemetry Collector, ClickHouse, Instana, k6 |
| Contenedores | Docker, Docker Compose |
| Pruebas automatizadas | Playwright, Vitest, Lighthouse |
| IA | LiteLLM como gateway hacia la API de Anthropic, con presupuestos y límites por usuario |
| Análisis de aplicaciones | mitmproxy, jadx, apktool, Ghidra |
| Sistemas | Linux (RHEL, Debian), Bash, Python, WSL2, cloud-init |

## En qué estoy trabajando

Un pipeline de GitHub Actions que se autentica en AWS por OIDC, revisa la infraestructura con Checkov, genera el SBOM de cada imagen con Syft y la firma con Cosign antes de publicarla.

## Contacto

[LinkedIn](https://www.linkedin.com/in/esquivelrodriguez123/)
