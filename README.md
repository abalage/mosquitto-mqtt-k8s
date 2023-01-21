# Usage

You can either use the plain YML files, or use [Kustomize](https://kustomize.io/).

An example of overwriting FQDN can be found in ˙overlay/kustomize.yml`

Deployment is tested on K3s-v1.24.8+k3s1.

## Usage

1. Create a namespace for Mosquitto:  
   ```kubectl create ns mosquitto```

2. Build the deployment by using kubectl's built-in kustomize feature:  
   ```kubectl apply -k overlay -n mosquitto```

If you are using this for Home Assistant then you can use the same namespace you already have for HA.

## Password authentication

After first run password authentication is set but /mosqitto/conf/password_file is empty.

Log into the container and use [mosquitto_passwd](https://mosquitto.org/man/mosquitto_passwd-1.html) utility to add users.

Alternatively if you already have password_file you can use the `overlay/password_file` too.
