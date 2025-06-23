# 🚀 Kubernetes Scaling, Autoscaling & Resource Management

This project/demo explores how to scale applications in Kubernetes using **Horizontal Pod Autoscaler (HPA)**, **Vertical Pod Autoscaler (VPA)**, and manage resources efficiently with **requests**, **limits**, and **Metrics Server**.

## 🔑 Key Concepts

### 📈 Scaling in Kubernetes
- **Horizontal Scaling (HPA):** Adds/removes pods based on metrics.
- **Vertical Scaling (VPA):** Adjusts CPU/Memory of existing pods.

### ⚖️ HPA vs VPA
| HPA                             | VPA                            |
|--------------------------------|--------------------------------|
| Scales pod count               | Scales pod resources           |
| Based on CPU/Memory/Custom     | Based on past usage            |
| Ideal for dynamic traffic      | Ideal for performance tuning   |

### 🧠 Metrics Server
- Collects resource usage (CPU, memory) data.
- Required for HPA to work.

### 💾 Resources: Requests & Limits
- **requests:** Guaranteed minimum resources.
- **limits:** Max allowed before OOM error.
- Prevents container resource overuse.

## 🔥 OOM Error Handling
Tested an OOM error scenario and learned how to:
- Set proper limits
- Restart crashed pods
- Observe pod status with `kubectl describe pod`

## 🤖 HPA in Action (Manual Demo)

```bash
kubectl autoscale deployment my-app --cpu-percent=50 --min=1 --max=5
