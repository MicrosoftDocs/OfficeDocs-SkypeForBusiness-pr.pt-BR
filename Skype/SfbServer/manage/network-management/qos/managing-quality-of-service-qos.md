---
title: Gerenciando a QoS (Qualidade de Serviço)
ms.reviewer: ''
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: A Qualidade de Serviço (QoS) é uma tecnologia de rede usada em algumas organizações para ajudar a fornecer a melhor experiência ao usuário final para comunicações de áudio e vídeo.
ms.openlocfilehash: aa7012a664c7075c06a6bd104921e1cac680e798
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60831975"
---
# <a name="managing-quality-of-service-qos-in-skype-for-business-server"></a>Gerenciando a qualidade do serviço (QoS) no Skype for Business Server


A Qualidade de Serviço (QoS) é uma tecnologia de rede usada em algumas organizações para ajudar a fornecer a melhor experiência ao usuário final para comunicações de áudio e vídeo. a QoS é usada mais frequentemente em rede com largura de banda limitada: com uma grande número de pacotes de rede para uma quantidade relativamente pequena de largura de banda disponível, a Qualidade de Serviço fornece aos administradores uma maneira de atribuírem prioridades mais altas a pacotes que carregam dados de áudio e vídeo. Ao conceder uma prioridade mais alta a esses pacotes, as comunicações de áudio e vídeo têm uma probabilidade maior de serem concluídas mais rápido e com menos interrupções do que as sessões de rede envolvendo itens como transferências de arquivos, navegação da Web ou backups de bancos de dados. Isso ocorre porque os pacotes de rede usados para transferências de arquivos ou backups de bancos de dados recebem uma atribuição de prioridade de "melhor esforço".


> [!NOTE]  
> Como regra geral, a Qualidade de Serviço se aplica somente a sessões de comunicação em sua rede interna. Ao implementar a QoS, você configure seus servidores e roteadores para suportar a marcação de pacotes; no entanto, você configura esses dispositivos para suportar a marcação de pacotes de forma específica. Não é possível considerar que a Qualidade de Serviço será suportada na Internet ou em outras redes. Mesmo se a Qualidade de Serviço for suportada em outras redes, não há garantia de que a QoS será configurada de forma igual a que você configurou o serviço em sua rede.

Skype for Business Server não exige Qualidade de Serviço; se você não usar a QoS no momento, não há nenhum requisito para instalar o serviço antes de instalar Skype for Business Server. Se você notar uma quantidade considerável de perda de pacotes em sua rede, a maneira recomendada de aliviar esse problema é adicionar mais largura de banda. Se não for possível adicionar mais largura de banda, então pode ser necessário implementar a Qualidade de Serviço.

Skype for Business Server oferece suporte completo para a Qualidade do Serviço: isso significa que as organizações que já estão usando a QoS podem facilmente integrar Skype for Business Server à infraestrutura de rede existente. Para fazer isso, você precisa executar as seguintes tarefas:

  - [Habilitando a QoS para dispositivos que não se baseiam em Windows](enabling-qos-for-devices-that-are-not-based-on-windows.md). Por padrão, a QoS está desativada para computadores e outros dispositivos (como iPhones) que executam outros sistemas operacionais. Embora você possa usar Skype for Business Server para habilitar e desabilitar a Qualidade do Serviço para dispositivos, normalmente não é possível usar o produto para modificar os códigos DSCP usados por esses dispositivos.

  - [Configurando intervalos de porta e uma política de Qualidade de Serviço para seus servidores de Conferência, Aplicativo e Mediação.](configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md) É necessário reservar um conjunto exclusivo de portas para tipos de pacotes diferentes, como áudio e vídeo. Com Skype for Business Server você não habilita ou desabilita a Qualidade do Serviço definindo um valor de propriedade como True ou False. Em vez disso, você ativa a Qualidade de Serviço configurando intervalos de porta e, em seguida, criando e aplicando a Política de grupo. Se decidir posteriormente não usar a QoS, você pode “desativar” a Qualidade de Serviço removendo os objetos de Política de grupo apropriados.

  - [Configurando intervalos de portas e uma política de Qualidade de Serviço para seus Servidores de Borda.](configuring-port-ranges-for-your-edge-servers.md) Embora não seja necessário, você pode configurar seus servidores de borda para usar os mesmos intervalos de porta que os outros servidores. A configuração de uma política de Qualidade de Serviço só deve ser feita para o lado interno dos servidores de Borda. Isso ocorre pois a Qualidade do Serviço foi projetada para uso em sua rede interna e não na Internet.

- [Configurando intervalos de porta e uma política de](configuring-port-ranges-for-your-skype-clients.md) Qualidade de Serviço para seus clientes em Skype for Business Server  Esses intervalos de porta aplicam-se apenas a computadores cliente e são normalmente diferentes dos intervalos de porta configurados em seus servidores. Observe que Skype for Business Server não dá suporte a QoS para Windows sistemas operacionais diferentes Windows 10.


