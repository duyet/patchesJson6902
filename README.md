# [`patchesStrategicMerge`](https://kubectl.docs.kubernetes.io/references/kustomize/kustomization/patchesstrategicmerge/)

```bash
$ cat ./using-patchesStrategicMerge/kustomization.yaml
# apiVersion: kustomize.config.k8s.io/v1beta1
# kind: Kustomization
# resources:
#   - ../overlay
# patchesStrategicMerge:
#   - pod.patch.yaml

$ kustomize build using-patchesStrategicMerge
```

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx
spec:
  containers:
  - env:
    - name: DEMO_HELLO
      value: Hello from patchesStrategicMerge
    - name: DEMO_GREETING
      value: Hello from the environment
    image: nginx:1.14.2
    name: nginx
    ports:
    - containerPort: 8080
    - containerPort: 80
```

# [`patchesJson6902`](https://kubectl.docs.kubernetes.io/references/kustomize/kustomization/patchesjson6902/)

```bash
$ cat ./using-patchesStrategicMerge/kustomization.yaml
# apiVersion: kustomize.config.k8s.io/v1beta1
# kind: Kustomization
# resources:
#   - ../overlay
# patchesStrategicMerge:
#   - pod.patch.yaml

$ kustomize build using-patchesJson6902
```

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx
spec:
  containers:
  - env:
    - name: DEMO_GREETING
      value: Hello from the environment
    - name: DEMO_HELLO
      value: Hello from patchesJson6902
    - name: NEW_ENV
      value: New Value
    image: nginx:1.14.2
    name: nginx
    ports:
    - containerPort: 80
```
