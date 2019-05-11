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
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: A qualidade do serviço (QoS) é uma tecnologia de rede usada em algumas organizações para ajudar a fornecer uma experiência de usuário final ideal para comunicações de áudio e vídeos.
ms.openlocfilehash: b63655cabbce642c05530adb80b94e8bfd1c34b8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913052"
---
# <a name="managing-quality-of-service-qos-in-skype-for-business-server"></a>Gerenciando a qualidade do serviço (QoS) no Skype para Business Server


A qualidade do serviço (QoS) é uma tecnologia de rede usada em algumas organizações para ajudar a fornecer uma experiência de usuário final ideal para comunicações de áudio e vídeos. QoS é mais comumente usada em redes onde está limitada a largura de banda: com um grande número de pacotes de rede competindo por uma quantidade relativamente pequena de largura de banda disponível, Quality of Service fornece uma maneira dos administradores atribuam prioridades mais altas aos pacotes transmitir dados de áudio ou vídeos. Dando esses pacotes uma prioridade mais alta, comunicações de áudio e vídeos tendem a conclusão mais rápida e com menos interrupção, que as sessões de rede envolvendo coisas como transferências de arquivos, navegação da web ou backups de banco de dados. Isso ocorre porque os pacotes de rede usados para transferências de arquivos ou backups de bancos de dados recebem uma atribuição de prioridade de "melhor esforço".


> [!NOTE]  
> Como regra geral, Quality of Service só se aplica a sessões de comunicação em sua rede interna. Quando você implementa a QoS, você configurar seus servidores e roteadores para oferecer suporte a marcação; de pacote No entanto, você pode configurar esses dispositivos para oferecer suporte a marcação de uma maneira particular de pacote. Você não pode assumir que Quality of Service terá suporte na Internet ou em outras redes. Mesmo se qualidade se o serviço é suportado em outras redes, há nenhuma garantia de QoS será configurado da mesma maneira que você configurou o serviço em sua rede.

Skype para Business Server não exige Quality of Service; Se você não usar QoS não há nenhum requisito que você instale o serviço antes de instalar o Skype para Business Server. Se você enfrentar uma quantidade considerável de perda de pacotes na rede a maneira recomendada para atenuar esse problema é adicionar a largura de banda adicional. Se não for possível adicionar mais largura de banda, convém implementar Quality of Service em vez disso.

Skype para Business Server oferece suporte completo para o Quality of Service: significa que as organizações que já estão usando o QoS podem facilmente integrar Skype para Business Server em sua infra-estrutura de rede existente. Para fazer isso, você deve executar as seguintes tarefas:

  - [Habilitando QoS para dispositivos que não são baseados no Windows](enabling-qos-for-devices-that-are-not-based-on-windows.md). Por padrão, a QoS é desativada em computadores e outros dispositivos (como iPhones) que executam outros sistemas operacionais. Embora você possa usar Skype para Business Server para habilitar e desabilitar o Quality of Service para dispositivos, você geralmente não é possível usar o produto para modificar os códigos DSCP usados por esses dispositivos.

  - [Configurando intervalos de porta e uma política de qualidade de serviço para seus servidores de conferência, o aplicativo e mediação](configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). É necessário reservar um conjunto exclusivo de portas para tipos de pacotes diferentes, como áudio e vídeo. Com o Skype para Business Server você, não, habilite ou desabilite Quality of Service, digamos, definir um valor de propriedade para True ou False. Em vez disso, você deve habilitar Quality of Service Configurando intervalos de porta e, em seguida, criando e aplicação da diretiva de grupo. Se posteriormente você decidir não usar a QoS você pode "Desativar" Quality of Service removendo os objetos de diretiva de grupo apropriados.

  - [Configurando intervalos de porta e uma política de qualidade de serviço para seus servidores de borda](configuring-port-ranges-for-your-edge-servers.md). Embora não seja necessário, você pode configurar seus servidores de borda para usar os mesmos intervalos de porta que os outros servidores. Configurar uma política de qualidade de serviço deve ser feito apenas para o lado interno dos seus servidores de borda. Isso acontece porque o Quality of Service é projetado para uso em sua rede interna e não na Internet.

- [Configurando intervalos de porta e uma política de qualidade de serviço para os clientes do Skype para Business Server](configuring-port-ranges-for-your-skype-clients.md)  Esses intervalos de portas se aplicam somente aos computadores clientes e são geralmente diferentes dos intervalos de porta configurados em seus servidores. Observe que Skype para Business Server não oferece suporte a sistemas operacionais de QoS para Windows que não seja Windows 10.


