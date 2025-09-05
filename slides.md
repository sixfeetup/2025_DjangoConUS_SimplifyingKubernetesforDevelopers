---
title-prefix: Six Feet Up
pagetitle: Simplifying Kubernetes for Developers
author: Calvin Hendryx-Parker, CTO, Six Feet Up
author-meta:
    - Calvin Hendryx-Parker
date: DjangoCon US 2025
date-meta: 2025
keywords:
    - Developer Experience
    - Kubernetes
    - Tilt
---

# Simplifying Kubernetes for Developers {.semi-filtered .r-fit-text data-background-image="images/1.png"}
#### Calvin Hendryx-Parker, CTO
#### Six Feet Up

::: notes
**Opening Hook (30 seconds)**: Acknowledge the elephant in the room. Show of hands: "How many of you think Kubernetes is too complicated?" Laugh with them, not at them. "You're absolutely right... but maybe not for the reasons you think."
:::

---

# The Problem: Developer Inner Loop {.r-fit-text data-background-image="images/2.png"}

**Docker workflow we love:**
- `docker build` → `docker run` → test → iterate

**Kubernetes reality:**
- `docker build` → `docker push` → `kubectl apply` → wait → debug → repeat

::: notes
**The Pain Point (1 minute)**: This is where I connect with their frustration. Docker gave us this beautiful fast feedback loop. But Kubernetes broke it. The problem isn't the complexity of orchestration - it's that we lost our fast inner development loop. Minutes instead of seconds. Push-wait-debug instead of instant feedback.
:::

---

# What Developers Actually Want {.r-fit-text data-background-image="images/3.png"}

- **Fast feedback loops** (seconds, not minutes)
- **Simple mental models** (`npm start`, `flask run`)  
- **Clear visibility** into what's running
- **Kubernetes benefits** without the friction

::: notes
**Reframe the Problem (1 minute)**: We don't hate complexity - we hate slow, opaque workflows. We want the benefits of K8s (scaling, networking, service discovery) but with a developer experience that doesn't suck. The problem isn't that Kubernetes is too complex - it's missing a developer experience layer.
:::

---

# Our Solution: Scaf + Tilt {.r-fit-text data-background-image="images/4.png"}

```bash
# Bootstrap a complete project with Tilt built-in
$ scaf myproject
```

```python
# Generated Tiltfile (already configured!)
docker_build('my-app', '.')
k8s_yaml('k8s/deployment.yaml')
k8s_resource('my-app')
```

```bash
$ tilt up
```

**From zero to full-stack Kubernetes in minutes.**

::: notes
**The Solution (1.5 minutes)**: This is where Six Feet Up's expertise shines. Scaf gives you a complete Django + K8s project template with Tilt pre-configured. Instead of fighting YAML and configuration, you get a batteries-included approach. One command gets you a production-ready project structure, and Tilt handles the development workflow.
:::

---

# What You Get with Scaf {.r-fit-text data-background-image="images/5.png"}

**Complete project template includes:**
- Django backend + optional Next.js frontend
- Kubernetes manifests (dev/staging/prod)
- **Tilt configuration** for instant development
- CI/CD pipelines, monitoring, database setup

**Development workflow:**
- Edit Django code → **live reload** in K8s cluster
- **Unified dashboard** for all services and logs

::: notes
**Show Don't Tell (1 minute)**: Scaf isn't just about Tilt - it's about eliminating ALL the setup friction. You get a complete, production-ready Django project with Kubernetes configuration that actually works. The Tilt integration means you can edit your Django models or views and see changes instantly in your cluster. No more "how do I set up Kubernetes for Django?" - it's all done.
:::

---

# The Real Problem Wasn't Complexity {.r-fit-text data-background-image="images/6.png"}

> Kubernetes isn't too complicated.  
> **It was missing bootstrapping and developer experience.**

**Scaf + Tilt = the complete solution**

### [github.com/sixfeetup/scaf](https://github.com/sixfeetup/scaf) | Open Source

::: notes
**The Takeaway (30 seconds)**: The problem was never Kubernetes complexity - it was the massive setup overhead and poor development workflows. Six Feet Up solved both: Scaf eliminates the bootstrap complexity, and Tilt gives you the fast development loop. Together, they make Kubernetes feel as easy as Django development should be.
:::

---

# Questions? {.r-fit-text data-background-image="images/8.png"}

### Calvin Hendryx-Parker, CTO, Six Feet Up
### [github.com/sixfeetup/scaf](https://github.com/sixfeetup/scaf)

::: notes
**Wrap Up**: Keep it brief, invite questions, and be ready to show more details about Scaf templates, Tilt configuration, or how this approach scales for Django teams. You can also mention Six Feet Up's expertise in Django and Kubernetes consulting.
:::


