--- 
page_type: Ejemplos
de lenguajes:
- azurecli
products:
- azure
---

# Ejemplo de Azure Well Architected Framework (extensión de script personalizada)

Este ejemplo de plantilla de Azure Resource Manager (ARM) implementa una máquina virtual Ubuntu y usa la extensión de script personalizada para instalar Nginx en la máquina virtual.

## Desplegar ejemplo

**Portal Azure**

Para implementar esta plantilla mediante el portal de Azure, haga clic en este botón.  

<br />

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https://raw.githubusercontent.com/mspnp/samples/master/OperationalExcellence/script-extension/azuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>  

**Azure CLI**

Clonar el repositorio de muestras.

```azurecli
git clone https://github.com/mspnp/samples.git
```

Cree un grupo de recursos para la implementación.

```azurecli
az group create --name boot-strap-script-extension --location eastus
```

Ejecute el siguiente comando para iniciar la implementación.

```azurecli
az deployment group create \
    --template-file ./samples/OperationalExcellence/script-extension/azuredeploy.json \
    --resource-group boot-strap-script-extension \
    --parameters adminUserName=adminuser adminPassword=Password2020!
```

Una vez hecho esto, el siguiente recurso se habrá implementado en su suscripción de Azure.

![Imagen de los recursos de Azure, tal como se ve en el portal de Azure.](./images/custom-script-demo-resources.png)

Busque la dirección IP pública de la máquina virtual para verificar que se haya instalado Nginx.

![Imagen de la página predeterminada de Nginx vista en un navegador web.](./images/nginx.png)

## Microsoft Open Source Code of Conduct

Este proyecto ha adoptado al [Código de conducta de código abierto de Microsoft]](https://opensource.microsoft.com/codeofconduct/).

Recursos:

- [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/)
- [Microsoft Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/)
- Contacto  [opencode@microsoft.com](mailto:opencode@microsoft.com) with questions or concerns
