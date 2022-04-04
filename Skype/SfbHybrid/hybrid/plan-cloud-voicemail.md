---
title: Planejar Caixa postal na Nuvem serviço para usuários locais| PBX Skype for Business Server 2019
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection: ''
description: Este artigo descreve benefícios, considerações de planejamento e requisitos para implementar o Caixa postal na Nuvem da Microsoft serviço. Para obter informações sobre como configurar Caixa postal na Nuvem, consulte Configuring Caixa postal na Nuvem.
ms.openlocfilehash: 4aefe6485dd4eee8321ea56bf12d68799a31de45
ms.sourcegitcommit: b0bb7db41856ee377dbe4ca8c9dff56385bf120d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2021
ms.locfileid: "61563730"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>Planejar Caixa postal na Nuvem serviço para usuários locais

## <a name="overview"></a>Visão geral

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Este artigo descreve benefícios, considerações de planejamento e requisitos para implementar o serviço Caixa postal na Nuvem da Microsoft para seus usuários locais. Para obter informações sobre como configurar Caixa postal na Nuvem, consulte [Configure Caixa postal na Nuvem service](configure-cloud-voicemail.md).

Caixa postal na Nuvem assume o lugar da Um (Unificação de Mensagens) Exchange ao fornecer a funcionalidade de mensagens de voz para usuários de voz do Skype for Business 2019 que têm caixas de correio no Exchange Server 2019 ou Exchange Online. Caixa postal na Nuvem oferece os seguintes benefícios para seus usuários locais e online:

- Funcionalidade de resposta e depósito de caixa postal com transcrição de fala aprimorada

- Acesso à caixa postal na caixa de correio do usuário Exchange usando o Skype for Business Online ou Outlook clientes

- A capacidade de usar o Centro de administração do Microsoft 365 para gerenciar opções de caixa postal

- Suporte para Exchange caixas de correio locais ou na nuvem

- Aproveitando as saudações de usuário existentes do Exchange Online Unificação de Mensagens

> [!Important]
> Skype for Business Online foi aposentado em 31 de julho de 2021. Os usuários não podem mais acessar a caixa postal na caixa de correio Exchange por meio do cliente Skype for Business Online.

Para obter mais informações sobre a comparação de recursos, consulte [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).

Skype for Business Server 2019 continua a usar Exchange UM para usuários cujas caixas de correio estão em versões anteriores do Exchange Server (2013, 2016).  Entender qual solução de caixa postal será usada com base na versão Exchange Server e Skype for Business Server é uma parte importante do planejamento da migração para o Skype for Business Server 2019 ou Exchange Server 2019. Para obter mais informações sobre migração e interoperabilidade, consulte [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).

Com Caixa postal na Nuvem, suas tarefas de administração são muito simplificadas porque:

- Não é necessário configurar a função Exchange UM.
- As tarefas de instalação para Caixa postal na Nuvem são mais simples.
- As atualizações para a funcionalidade da caixa postal são entregues diretamente na nuvem, portanto, seus usuários sempre têm acesso aos recursos mais recentes e atualizações com menos dependência de Atualizações Cumulativas (CUs).
- Você tem o mesmo conjunto de controles para caixas de correio locais e Exchange online. Para obter mais informações sobre esses controles, consulte [Configurar Sistema de Telefonia caixa postal](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d).

O diagrama a seguir mostra Caixa postal na Nuvem em uma implantação híbrida:

![SfB Caixa postal na Nuvem.](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

As chamadas não respondidas são tratadas da seguinte forma:  

1. Para usuários que estão Skype for Business 2019 no local, as chamadas não respondidas são enviadas pelo serviço de Skype for Business Server local para o serviço de Caixa postal na Nuvem online.
2. O serviço processa a caixa postal, incluindo transcrição.
3. Em seguida, o serviço deposita a caixa postal Exchange caixa de correio do usuário, se a caixa de correio está no local ou online.  
4. Os usuários podem acessar a caixa postal de seus clientes Skype for Business ou Outlook cliente.

## <a name="requirements"></a>Requirements

Os requisitos a seguir pressuem que você já Skype for Business Server implantado em uma topologia suportada.  Seus requisitos dependem do cenário:

- Se você já estiver usando Exchange UM online e atualizar para o Skype for Business 2019, precisará modificar sua política de caixa postal hospedada e verificar se seus provedores de hospedagem estão definidos corretamente. Para obter mais informações, consulte [Configure Caixa postal na Nuvem service](configure-cloud-voicemail.md).

- Se você estiver usando Exchange UM no local ou tiver uma combinação de usuários usando Exchange UM online e local, será necessário modificar a política de caixa postal hospedada e o provedor de hospedagem.  Para obter mais informações, consulte [Configure Caixa postal na Nuvem service](configure-cloud-voicemail.md).

- Para uma nova configuração de Caixa postal na Nuvem, siga as etapas descritas em [Configure Caixa postal na Nuvem service](configure-cloud-voicemail.md).

Além dos requisitos acima, os requisitos a seguir devem ser configurados para se conectar ao Caixa postal na Nuvem da Microsoft serviço:

- Conectividade híbrida. Se você já tiver Skype for Business Server implantado e quiser habilitar o Caixa postal na Nuvem para seus usuários locais, certifique-se de ter a conectividade híbrida configurada entre seus ambientes locais e online. Às vezes, isso é chamado de configuração de domínio dividido.

   Para obter mais informações, consulte [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).

- Os usuários locais devem estar habilitados para Enterprise Voice e Caixa Postal Hospedada em Skype for Business Server.

- Uma URL Exchange EWS (Serviços Web Externos) e Descoberta Automática devem ser configuradas ou alguns recursos Caixa postal na Nuvem serão limitados.

- Se você tiver um servidor Exchange local, Caixa postal na Nuvem as etapas em Configurar o Caixa postal na Nuvem para Exchange Server [de Caixa de Correio](/microsoftteams/set-up-phone-system-voicemail#set-up-cloud-voicemail-for-exchange-server-mailbox-users).

## <a name="migration-and-interoperability"></a>Migração e interoperabilidade

Se você estiver planejando implantar o Skype for Business Server 2019 e/ou Exchange Server 2019, planeje sua migração com cuidado para garantir o serviço contínuo para mensagens de voz. Lembre-se do seguinte:

- Exchange Server 2019 não fornece mais Exchange funcionalidade de UM
- Skype for Business Server 2019 não se integra mais ao Exchange Online UM

Interoperabilidade de versão e topologias com suporte para Caixa postal na Nuvem estão listadas na tabela a seguir, que compara as versões Skype for Business Server em que o usuário pode estar em casa com a versão possível fornecendo sua caixa de correio Exchange. Você precisa usar Caixa postal na Nuvem se quiser usar o Skype for Business 2019 com Exchange Online ou Exchange Server 2019.

| Skype/versão do Lync | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| Skype for Business Server 2019 | Exchange Server UM | Exchange Server UM | Caixa Postal na Nuvem | Caixa Postal na Nuvem |
| Skype for Business Server 2015 | Exchange Server UM | Exchange Server UM | Sem suporte | Caixa Postal na Nuvem |
| Lync Server 2013 <br>  | Exchange Server UM | Exchange Server UM | Não Suportado | Caixa Postal na Nuvem |

A Microsoft recomenda os seguintes caminhos de migração:

- Se você estiver atualizando para o Skype for Business Server 2019, poderá usar Exchange UM no Exchange Server 2013 ou 2016, mas deverá atualizar para o Caixa postal na Nuvem se estiver usando o Exchange Server 2019.
- Se você estiver atualizando para o Exchange Server 2019 e estiver usando versões anteriores da UM do Exchange Server para mensagens de voz do Skype for Business Server, a Microsoft recomenda que você atualize para o Skype for Business Server 2019 antes da atualização da caixa de correio.  Caso contrário, os recursos de mensagens de voz serão perdidos.
- Se você estiver atualizando para o Skype for Business Server 2019 e tiver o Skype for Business Server 2015 configurado para caixa postal com Exchange Online UM, a caixa postal dos usuários migrará automaticamente da UM Exchange Online para Caixa postal na Nuvem quando sua conta é movida para Skype for Business Server 2019. 

Para obter mais informações sobre como planejar sua migração, consulte [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).