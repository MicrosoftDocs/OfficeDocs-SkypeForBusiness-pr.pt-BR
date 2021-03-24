---
title: Planejar o serviço de Caixa Postal na Nuvem para usuários locais| PBX Skype for Business Server 2019
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Este artigo descreve benefícios, considerações de planejamento e requisitos para implementar o serviço Microsoft Cloud Voicemail. Para obter informações sobre como configurar a Caixa Postal na Nuvem, consulte Configuring Cloud Voicemail.
ms.openlocfilehash: 4ae274f33d2b7d52c486cd9031d01bc3a532a6b3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110277"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>Planejar o serviço de Caixa Postal na Nuvem para usuários locais

## <a name="overview"></a>Visão geral

Este artigo descreve benefícios, considerações de planejamento e requisitos para implementar o serviço microsoft cloud voicemail para seus usuários locais. Para obter informações sobre como configurar a Caixa Postal na Nuvem, consulte [Configure Cloud Voicemail service](configure-cloud-voicemail.md).

A Caixa Postal na Nuvem assume o lugar da Unificação de Mensagens do Exchange (UM) no fornecimento da funcionalidade de mensagens de voz para usuários de voz do Skype for Business 2019 que têm caixas de correio no Exchange Server 2019 ou no Exchange Online. A Caixa Postal na Nuvem oferece os seguintes benefícios para seus usuários locais e online:

- Funcionalidade de resposta e depósito de caixa postal com transcrição de fala aprimorada

- Acesso à caixa postal na caixa de correio do Exchange do usuário usando os clientes do Skype for Business Online ou do Outlook

- A capacidade de usar o Centro de administração do Microsoft 365 para gerenciar opções de caixa postal

- Suporte para caixas de correio do Exchange no local ou na nuvem

- Aproveitando as saudações de usuário existentes da Unificação de Mensagens do Exchange Online

> [!Important]
> O Skype for Business Online será reformado em 31 de julho de 2021 após o qual os usuários não poderão mais acessar a caixa postal em sua caixa de correio do Exchange por meio do cliente Skype for Business Online.

Para obter mais informações sobre a comparação de recursos, consulte [Plan for Skype for Business Server e Exchange Server migration](plan-um-migration.md).

O Skype for Business Server 2019 continua a usar a UM do Exchange para usuários cujas caixas de correio estão em versões anteriores do Exchange Server (2013, 2016).  Entender qual solução de caixa postal será usada com base na versão do Exchange Server e do Skype for Business Server é uma parte importante do planejamento da migração para o Skype for Business Server 2019 ou Exchange Server 2019. Para obter mais informações sobre migração e interoperabilidade, consulte [Plan for Skype for Business Server e Exchange Server migration](plan-um-migration.md).

Com a Caixa Postal na Nuvem, suas tarefas de administração são muito simplificadas porque:

- Não é necessário configurar a função de UM do Exchange.
- As tarefas de instalação do Cloud Voicemail são mais simples.
- As atualizações para a funcionalidade da caixa postal são entregues diretamente na nuvem, portanto, seus usuários sempre têm acesso aos recursos mais recentes e atualizações com menos dependência de Atualizações Cumulativas (CUs).
- Você tem o mesmo conjunto de controles para caixas de correio locais e online do Exchange. Para obter mais informações sobre esses controles, consulte [Configurar caixa postal do Sistema de Telefonia](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d).

O diagrama a seguir mostra o Cloud Voicemail em uma implantação híbrida:

![Caixa postal de nuvem SfB](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

As chamadas não respondidas são tratadas da seguinte forma:  

1. Para usuários que estão no Skype for Business 2019 no local, as chamadas não respondidas são enviadas pelo Skype for Business Server local para o serviço online de Caixa Postal na Nuvem.
2. O serviço processa a caixa postal, incluindo transcrição.
3. Em seguida, o serviço deposita a caixa postal na caixa de correio do Exchange do usuário, se a caixa de correio está local ou online.  
4. Os usuários podem acessar suas mensagens de voz a partir de seus clientes do Skype for Business ou do Outlook.

## <a name="requirements"></a>Requisitos

Os requisitos a seguir pressuem que você já tenha o Skype for Business Server implantado em uma topologia com suporte.  Seus requisitos dependem do cenário:

- Se você já estiver usando a UM do Exchange online e atualizar para o Skype for Business 2019, precisará modificar sua política de caixa postal hospedada e verificar se seus provedores de hospedagem estão definidos corretamente. Para obter mais informações, consulte [Configure Cloud Voicemail service](configure-cloud-voicemail.md).

- Se você estiver usando a UM do Exchange no local ou tiver uma combinação de usuários usando a UM do Exchange online e no local, será necessário modificar a política de caixa postal hospedada e o provedor de hospedagem.  Para obter mais informações, consulte [Configure Cloud Voicemail service](configure-cloud-voicemail.md).

- Para uma nova configuração do Cloud Voicemail, siga as etapas descritas em [Configure Cloud Voicemail service](configure-cloud-voicemail.md).

Além dos requisitos acima, os requisitos a seguir devem ser configurados para se conectar ao serviço microsoft cloud voicemail:

- Conectividade híbrida. Se você já tiver o Skype for Business Server implantado e quiser habilitar a Caixa Postal na Nuvem para seus usuários locais, você deve garantir que a conectividade híbrida seja configurada entre seus ambientes locais e online. Às vezes, isso é chamado de configuração de domínio dividido.

   Para obter mais informações, consulte [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).

- Os usuários locais devem estar habilitados para Enterprise Voice e Caixa Postal Hospedada no Skype for Business Server.

- Uma URL e a Descoberta Automática dos Serviços Web do Exchange Externos (EWS) devem ser configuradas ou alguns recursos de Caixa Postal na Nuvem serão limitados.

- Se você tiver um servidor Exchange local, configurar a Caixa Postal na Nuvem usando as etapas em Configurar a Caixa Postal na Nuvem para usuários Exchange Server [caixa de correio.](/microsoftteams/set-up-phone-system-voicemail#set-up-cloud-voicemail-for-exchange-server-mailbox-users)

## <a name="migration-and-interoperability"></a>Migração e interoperabilidade

Se você estiver planejando implantar o Skype for Business Server 2019 e/ou Exchange Server 2019, planeje sua migração com cuidado para garantir o serviço contínuo para mensagens de voz. Lembre-se do seguinte:

- Exchange Server 2019 não fornece mais a funcionalidade de UM do Exchange
- O Skype for Business Server 2019 não se integra mais à UM do Exchange Online

Interoperabilidade de versão e topologias com suporte para a Caixa Postal na Nuvem estão listadas na tabela a seguir, que compara as versões do Skype for Business Server em que o usuário pode estar em casa com a versão possível fornecendo sua Caixa de Correio do Exchange. Você precisa usar o Cloud Voicemail se quiser usar o Skype for Business 2019 com o Exchange Online ou Exchange Server 2019.

| | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| Skype for Business Server 2019 | Exchange Server UM | Exchange Server UM | Caixa Postal em Nuvem | Caixa Postal em Nuvem |
| Skype for Business Server 2015 | Exchange Server UM | Exchange Server UM | Sem suporte | Caixa Postal em Nuvem |
| Lync Server 2013 <br>  | Exchange Server UM | Exchange Server UM | Não suportado | Caixa Postal em Nuvem |

A Microsoft recomenda os seguintes caminhos de migração:

- Se você estiver atualizando para o Skype for Business Server 2019, poderá usar a UM do Exchange no Exchange Server 2013 ou 2016, mas deverá atualizar para o Cloud Voicemail se estiver usando o Exchange Server 2019.
- Se você estiver atualizando para o Exchange Server 2019 e estiver usando versões anteriores do Exchange Server UM para mensagens de voz do Skype for Business Server, a Microsoft recomenda que você atualize para o Skype for Business Server 2019 antes da atualização da caixa de correio.  Caso contrário, os recursos de mensagens de voz serão perdidos.
- Se você estiver atualizando para o Skype for Business Server 2019 e tiver o Skype for Business Server 2015 configurado para caixa postal com a UM do Exchange Online, a caixa postal dos usuários migrará automaticamente da UM do Exchange Online para a Caixa Postal na Nuvem quando sua conta for movida para o Skype for Business Server 2019. 

Para obter mais informações sobre como planejar sua migração, consulte [Plan for Skype for Business Server e Exchange Server migration.](plan-um-migration.md)