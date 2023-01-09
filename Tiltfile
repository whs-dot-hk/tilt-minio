def create_namespace(name):
    k8s_yaml(blob("""apiVersion: v1
kind: Namespace
metadata:
  name: %s
""" % name))

name = "minio"

create_namespace(name)

k8s_yaml(helm("charts/operator", name = "%s-operator" % name, namespace = name))
k8s_yaml(helm("charts/tenant", name = "%s-tenant" % name, namespace = name))
