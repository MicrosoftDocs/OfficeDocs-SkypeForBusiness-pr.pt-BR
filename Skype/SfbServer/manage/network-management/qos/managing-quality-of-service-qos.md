---
title: Gerenciando a qualidade do serviço (QoS)
ms.reviewer: ''
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: A QoS (qualidade de serviço) é uma tecnologia de rede usada em algumas organizações para ajudar a oferecer uma experiência ideal para o usuário final para comunicações de áudio e vídeo.
ms.openlocfilehash: 821ebb1cd6a101856f4fbc4fb3428ecba7674245
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817357"
---
# <a name="managing-quality-of-service-qos-in-skype-for-business-server"></a>Gerenciando a qualidade do serviço (QoS) no Skype for Business Server


A QoS (qualidade de serviço) é uma tecnologia de rede usada em algumas organizações para ajudar a oferecer uma experiência ideal para o usuário final para comunicações de áudio e vídeo. A QoS é mais comumente usada em redes em que a largura de banda é limitada: com um grande número de pacotes de rede competindo por uma quantidade relativamente pequena de largura de banda disponível, a qualidade do serviço fornece uma maneira para os administradores atribuirem prioridades maiores aos pacotes transportar dados de áudio ou vídeo. Ao fornecer esses pacotes, é provável que as comunicações de áudio e vídeo sejam concluídas com mais rapidez e menos interrupções do que as sessões de rede envolvendo itens como transferências de arquivos, navegação na Web ou backups de banco de dados. Isso ocorre porque os pacotes de rede usados para transferências de arquivos ou backups de bancos de dados recebem uma atribuição de prioridade de "melhor esforço".


> [!NOTE]  
> Como regra geral, a qualidade do serviço aplica-se somente a sessões de comunicação em sua rede interna. Ao implementar QoS, você configura seus servidores e roteadores para dar suporte à marcação de pacotes; no entanto, você configura esses dispositivos para dar suporte à marcação de pacotes de uma maneira específica. Você não pode supor que a qualidade do serviço será compatível na Internet ou em outras redes. Mesmo que o serviço de qualidade seja compatível com outras redes, não há garantia de que a QoS será configurada da mesma maneira que você configurou o serviço na sua rede.

O Skype for Business Server não requer qualidade de serviço; Se você não usa o QoS no momento, não há necessidade de instalar o serviço antes de instalar o Skype for Business Server. Se você tiver uma quantidade considerável de perda de pacotes na rede, a maneira recomendada de aliviar esse problema é adicionar mais largura de banda. Se não for possível adicionar mais largura de banda, talvez você queira implementar a qualidade do serviço em vez disso.

O Skype for Business Server oferece suporte total para a qualidade do serviço: isso significa que as organizações que já estão usando a QoS podem integrar facilmente o Skype for Business Server à infraestrutura de rede existente. Para fazer isso, você deve executar as seguintes tarefas:

  - [Habilitando a QoS para dispositivos que não são baseados no Windows](enabling-qos-for-devices-that-are-not-based-on-windows.md). Por padrão, a QoS é desativada em computadores e outros dispositivos (como iPhones) que executam outros sistemas operacionais. Embora você possa usar o Skype for Business Server para habilitar e desabilitar a qualidade do serviço para dispositivos, normalmente não é possível usar o produto para modificar os códigos DSCP usados por esses dispositivos.

  - [Configurar intervalos de porta e uma política de qualidade de serviço para seus servidores de conferência, aplicativo e mediação](configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). É necessário reservar um conjunto exclusivo de portas para tipos de pacotes diferentes, como áudio e vídeo. Com o Skype for Business Server, você não habilita ou desabilita a qualidade do serviço por, digamos, definir um valor de propriedade como verdadeiro ou falso. Em vez disso, habilite a qualidade de serviço Configurando intervalos de porta e, em seguida, criando e aplicando a política de grupo. Se, mais tarde, você decidir não usar o QoS, poderá "Desabilitar" a qualidade do serviço simplesmente removendo os objetos de política de grupo apropriados.

  - [Configurar intervalos de porta e uma política de qualidade de serviço para seus servidores de borda](configuring-port-ranges-for-your-edge-servers.md). Embora não seja necessário, você pode configurar seus servidores de borda para usar os mesmos intervalos de porta que os outros servidores. A configuração de uma política de qualidade de serviço só deve ser feita para o lado interno dos seus servidores Edge. Isso porque a qualidade do serviço foi projetada para ser usada em sua rede interna e não na Internet.

- [Configurando intervalos de porta e uma política de qualidade de serviço para seus clientes no Skype for Business Server](configuring-port-ranges-for-your-skype-clients.md)  Esses intervalos de portas se aplicam apenas aos computadores cliente e são normalmente diferentes dos intervalos de porta configurados em seus servidores. Observe que o Skype for Business Server não é compatível com QoS para sistemas operacionais Windows que não sejam o Windows 10.


