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
description: Este artigo descreve os benefícios, considerações de planejamento e requisitos para implementar o serviço de Caixa Postal do Microsoft Cloud. Para obter informações sobre como configurar a caixa postal na nuvem, consulte Configurando a caixa postal na nuvem.
ms.openlocfilehash: 8a75c670448cf69cf6d9d772c670c9451fd94f80
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662086"
---
# <a name="plan-cloud-voicemail-service-for-on-premises-users"></a>Planejar o serviço de Caixa Postal na Nuvem para usuários locais

## <a name="overview"></a>Visão geral

Este artigo descreve os benefícios, considerações de planejamento e requisitos para implementar o serviço de Caixa Postal do Microsoft Cloud para seus usuários locais. Para obter informações sobre como configurar a caixa postal na nuvem, consulte [Configurar o serviço de caixa postal na nuvem.](configure-cloud-voicemail.md)

A Caixa Postal na Nuvem assume o lugar da Unificação de Mensagens (UM) do Exchange no fornecimento de funcionalidade de mensagens de voz para usuários de voz do Skype for Business 2019 que possuem caixas de correio no Exchange Server 2019 ou no Exchange Online. A Caixa Postal na Nuvem oferece os seguintes benefícios para os usuários locais e online:

- Funcionalidade de resposta e depósito de caixa postal com transcrição de fala aprimorada

- Acesso à caixa postal na caixa de correio do Exchange do usuário usando os clientes do Skype for Business Online ou do Outlook

- A capacidade de usar o Centro de administração do Microsoft 365 para gerenciar opções de caixa postal

- Suporte para caixas de correio do Exchange no local ou na nuvem

- Aproveitando saudações de usuário existentes da Unificação de Mensagens do Exchange Online

> [!Important]
> O Skype for Business Online será retirado em 31 de julho de 2021, após o qual os usuários não poderão mais acessar a caixa postal em suas caixas de correio do Exchange por meio do cliente Skype for Business Online.

Para obter mais informações sobre comparação de recursos, [consulte Planejar a migração do Skype for Business Server e do Exchange Server.](plan-um-migration.md)

O Skype for Business Server 2019 continua a usar a UM do Exchange para usuários cujas caixas de correio estão em versões anteriores do Exchange Server (2013, 2016).  Compreender qual solução de caixa postal será usada com base na versão do Exchange Server e do Skype for Business Server é uma parte importante do planejamento da migração para o Skype for Business Server 2019 ou o Exchange Server 2019. Para obter mais informações sobre migração e interoperabilidade, consulte [Planejar a migração do Skype for Business Server e do Exchange Server.](plan-um-migration.md)

Com a Caixa Postal na Nuvem, suas tarefas de administração são bastante simplificadas porque:

- Não é necessário configurar a função UM do Exchange.
- As tarefas de configuração da Caixa Postal na Nuvem são mais simples.
- As atualizações da funcionalidade de caixa postal são entregues diretamente na nuvem, para que os usuários sempre tenham acesso aos recursos e atualizações mais recentes com menos dependência de Atualizações Cumulativas (CUs).
- Você tem o mesmo conjunto de controles para caixas de correio locais e online do Exchange. Para obter mais informações sobre esses controles, consulte Configurar a [caixa postal do Sistema de Telefonia.](https://support.office.com/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d)

O diagrama a seguir mostra a Caixa Postal na Nuvem em uma implantação híbrida:

![Caixa postal na nuvem do SfB](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

As chamadas não respondidas são tratadas da seguinte forma:  

1. Para usuários que estão no Skype for Business 2019 local, as chamadas não respondidas são enviadas pelo Skype for Business Server local para o serviço online de Caixa Postal na Nuvem.
2. O serviço processa a caixa postal, incluindo transcrição.
3. Em seguida, o serviço deposita a caixa postal na caixa de correio do Exchange do usuário, se a caixa de correio está no local ou online.  
4. Os usuários podem acessar suas mensagens de voz no cliente do Skype for Business ou do Outlook.

## <a name="requirements"></a>Requisitos

Os requisitos a seguir presumem que você já tenha implantado o Skype for Business Server em uma topologia com suporte.  Seus requisitos dependem do seu cenário:

- Se você já estiver usando a UM do Exchange online e atualizar para o Skype for Business 2019, será necessário modificar sua política de caixa postal hospedada e verificar se seus provedores de hospedagem estão definidos corretamente. Para obter mais informações, consulte [Configurar o serviço de Caixa Postal na Nuvem.](configure-cloud-voicemail.md)

- Se você estiver usando a UM do Exchange no local ou tiver uma combinação de usuários usando a UM do Exchange online e local, será necessário modificar a política de caixa postal hospedada e o provedor de hospedagem.  Para obter mais informações, consulte [Configurar o serviço de Caixa Postal na Nuvem.](configure-cloud-voicemail.md)

- Para uma nova configuração de Caixa Postal na Nuvem, siga as etapas descritas em [Configurar o serviço de Caixa Postal na Nuvem.](configure-cloud-voicemail.md)

Além dos requisitos acima, os requisitos a seguir devem ser configurados para se conectar ao serviço de Caixa Postal do Microsoft Cloud:

- Conectividade híbrida. Se você já implantou o Skype for Business Server e deseja habilitar a Caixa Postal na Nuvem para seus usuários locais, você deve garantir que tenha uma conectividade híbrida configurada entre seus ambientes locais e online. Isso algumas vezes é chamado de configuração de domínio dividido.

   Para obter mais informações, consulte Planejar a conectividade híbrida entre o Skype for Business Server e o [Microsoft 365 ou Office 365](plan-hybrid-connectivity.md) e configurar a conectividade híbrida entre o Skype for Business Server e o [Office 365.](configure-hybrid-connectivity.md)

- Os usuários locais devem estar habilitados para Enterprise Voice e Caixa Postal Hospedada no Skype for Business Server.

- Uma URL dos Serviços Web do Exchange (EWS) externa e a Descoberta Automática devem ser configuradas ou alguns recursos de Caixa Postal na Nuvem serão limitados.

- Se você tiver um servidor exchange local, configurar a caixa postal na nuvem usando as etapas em Configurar caixa postal na nuvem para usuários de caixa de correio do [Exchange Server](https://docs.microsoft.com/microsoftteams/set-up-phone-system-voicemail#set-up-cloud-voicemail-for-exchange-server-mailbox-users).

## <a name="migration-and-interoperability"></a>Migração e interoperabilidade

Se estiver planejando implantar o Skype for Business Server 2019 e/ou o Exchange Server 2019, planeje sua migração com cuidado para garantir o serviço continuado para mensagens de voz. Lembre-se do seguinte:

- O Exchange Server 2019 não oferece mais funcionalidade de UM do Exchange
- O Skype for Business Server 2019 não se integra mais à UM do Exchange Online

A interoperabilidade de versão e as topologias com suporte para Caixa Postal na Nuvem estão listadas na tabela a seguir, que compara as versões do Skype for Business Server em que o usuário pode estar instalado com a possível versão que fornece sua Caixa de Correio do Exchange. Você precisará usar a Caixa Postal na Nuvem se quiser usar o Skype for Business 2019 com o Exchange Online ou o Exchange Server 2019.

| | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| Skype for Business Server 2019 | Exchange Server UM | Exchange Server UM | Caixa Postal em Nuvem | Caixa Postal em Nuvem |
| Skype for Business Server 2015 | Exchange Server UM | Exchange Server UM | Sem suporte | Caixa Postal em Nuvem |
| Lync Server 2013 <br>  | Exchange Server UM | Exchange Server UM | Não suportado | Caixa Postal em Nuvem |

A Microsoft recomenda os seguintes caminhos de migração:

- Se você estiver atualizando para o Skype for Business Server 2019, poderá usar a UM do Exchange no Exchange Server 2013 ou 2016, mas deverá atualizar para a Caixa Postal na Nuvem se estiver usando o Exchange Server 2019.
- Se você estiver atualizando para o Exchange Server 2019 e estiver usando versões anteriores do UM do Exchange Server para mensagens de voz do Skype for Business Server, a Microsoft recomenda atualizar para o Skype for Business Server 2019 antes da atualização da caixa de correio.  Caso contrário, os recursos de mensagens de voz serão perdidos.
- Se você estiver atualizando para o Skype for Business Server 2019 e tiver o Skype for Business Server 2015 configurado para caixa postal com a UM do Exchange Online, a caixa postal dos usuários migrará automaticamente da UM do Exchange Online para a Caixa Postal na Nuvem quando sua conta for movida para o Skype for Business Server 2019. 

Para obter mais informações sobre como planejar sua migração, consulte [Planejar a migração do Skype for Business Server e do Exchange Server.](plan-um-migration.md)
