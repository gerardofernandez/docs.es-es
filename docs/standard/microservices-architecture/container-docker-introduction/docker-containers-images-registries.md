---
title: Contenedores, imágenes y registros de Docker
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Contenedores, imágenes y registros de Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 4716159d052fd8e229ac42e5d17c72717ac86d9f
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106465"
---
# <a name="docker-containers-images-and-registries"></a>Contenedores, imágenes y registros de Docker

Al usar Docker, un desarrollador crea una aplicación o un servicio y lo empaqueta, junto con sus dependencias, en una imagen de contenedor. Una imagen es una representación estática de la aplicación o el servicio y de su configuración y las dependencias.

Para ejecutar la aplicación o el servicio, se crea una instancia de la imagen de la aplicación para crear un contenedor, que se ejecutará en el host de Docker. Inicialmente, los contenedores se prueban en un entorno de desarrollo o un PC.

Los desarrolladores deben almacenar las imágenes en un registro, que actúa como una biblioteca de imágenes y es necesario cuando se implementa en orquestadores de producción. Docker mantiene un registro público a través de [Docker Hub](https://hub.docker.com/); otros proveedores ofrecen registros para distintas colecciones de imágenes. Como alternativa, las empresas pueden tener un registro privado local para sus propias imágenes de Docker.

En la figura 2-4 se muestra cómo se relacionan las imágenes y los registros de Docker con otros componentes. También se muestran las diversas ofertas de registro de los proveedores.

![](./media/image5.PNG)

**Figura 2-4**. Taxonomía de términos de Docker y conceptos

Colocar imágenes en un registro le permite almacenar fragmentos de la aplicación que son estáticos e inmutables, incluidas todas sus dependencias a nivel de marco. Después, esas imágenes se pueden versionear e implementar en varios entornos y, por tanto, proporcionar una unidad de implementación coherente.

Los registros de imágenes privados, ya sean hospedados localmente o en la nube, se recomiendan cuando:

-   Las imágenes no deben compartirse públicamente por motivos de confidencialidad.

-   Quiere tener una latencia de red mínima entre las imágenes y el entorno de implementación elegido. Por ejemplo, si el entorno de producción es la nube de Azure, probablemente quiera almacenar las imágenes en Azure Container Registry, para que la latencia de red sea mínima. De forma similar, si el entorno de producción es local, puede tener un registro de confianza de Docker local disponible dentro de la misma red local.

>[!div class="step-by-step"]
[Anterior](docker-terminology.md)
[Siguiente](../net-core-net-framework-containers/index.md)
