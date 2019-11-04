---
title: Voz na nuvem no Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
ms.reviewer: crowe
f1keywords:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
search.appverid: MET150
description: Página de aterrissagem para implantar a voz na nuvem no Microsoft Teams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 969d55f41226d1c6effaf4c183992f15bf48e385
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925572"
---
# <a name="cloud-voice-in-microsoft-teams"></a>Voz na nuvem no Microsoft Teams

Você concluiu a [Introdução](get-started-with-teams-quick-start.md). Você implementou o Teams com [chat, equipes, canais e aplicativos](deploy-chat-teams-channels-microsoft-teams-landing-page.md) na organização. Talvez você tenha implantado [reuniões & conferência](deploy-meetings-microsoft-teams-landing-page.md). Agora você está pronto para adicionar recursos de voz em nuvem para seus usuários. 

A Cloud Voice oferece recursos de PBX (Private Branch Exchange) e opções para conexão à rede telefônica pública comutada (PSTN).

Este artigo ajuda você a decidir se precisa alterar qualquer uma das configurações de voz de nuvem padrão, com base nas necessidades de negócios e perfil da sua organização, e o orienta durante cada alteração. Dividimos as configurações em dois grupos, começando pelo conjunto básico de [alterações que você tem mais probabilidade de fazer](#core-deployment-decisions). O segundo grupo inclui [configurações adicionais](#additional-deployment-decisions) que poderão ser configuradas com base nas necessidades de sua organização.

Recomendamos que todas as organizações funcionem pelas decisões básicas e, se a sua organização tiver requisitos adicionais, revise o material a seguir.



## <a name="learn-more-about-cloud-voice"></a>Saiba mais sobre a voz na nuvem

Os artigos a seguir fornecem mais informações sobre a implantação e o uso de recursos de voz na nuvem no Teams:

- [Sistema de telefonia no Office 365](what-is-phone-system-in-office-365.md)
- [Sistema de Telefonia com Planos de Chamadas](calling-plan-landing-page.md)
- [Roteamento Direto do Sistema Telefônico](direct-routing-landing-page.md)
- [Implantação do Cloud Voice](cloud-voice-deployment.md)
- [Soluções de telefonia da Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)
- Assista à sessão a seguir para saber mais sobre o sistema telefônico: [introdução ao sistema telefônico no Microsoft Teams](https://aka.ms/teams-phone-system)


## <a name="core-deployment-decisions"></a>Decisões importantes sobre implantação

Estas são as configurações que a maioria das organizações deseja alterar (se as configurações padrão do Teams não atenderem às necessidades da organização).

## <a name="phone-system-office-365"></a>Sistema telefônico (Office 365)

O sistema de telefonia é a tecnologia da Microsoft para habilitar os recursos de controle de chamada e PBX (Private Branch Exchange) na nuvem do Office 365. O sistema telefônico permite substituir seu sistema de PBX (Exchange Branch Exchange) existente por um conjunto de recursos entregues diretamente do Office 365 e totalmente integrado à experiência de produtividade na nuvem da empresa.


|Pergunte-se|Ação |
|:------------|:-------|
|Em quais locais e escritórios do usuário devo implementar o sistema telefônico? |Para obter mais informações sobre o sistema telefônico, consulte [o que é o sistema telefônico no Office 365](what-is-phone-system-in-office-365.md).</li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a>Conexão com a rede telefônica pública comutada (PSTN)

Para conectar o sistema telefônico à rede telefônica pública comutada (PSTN) para que os usuários possam fazer chamadas telefônicas pelo mundo, você tem opções com base na necessidade dos seus negócios.  Pergunte-se o seguinte:


|Pergunte-se|Ação |
| :------------|:-------|
| Desejo usar o plano de chamadas da Microsoft como minha operadora de telefonia? | Para obter mais informações, consulte [sistema telefônico com planos de chamada](calling-plan-landing-page.md).|
| Preciso usar minha própria operadora de telefonia? | Para obter mais informações, consulte [sistema telefônico com roteamento direto](direct-routing-landing-page.md).
|||


## <a name="additional-deployment-decisions"></a>Decisões adicionais de implantação

Talvez você queira alterar as configurações para o seguinte, com base nas necessidades e configuração da sua organização:

- Caixa postal
- Identidade de chamada
- Números de telefone da Microsoft
- Planos de discagem
- Filas de chamadas
- Atendedores automáticos

### <a name="voicemail"></a>Caixa postal

O correio de voz na nuvem, da plataforma de correio de voz do Azure, oferece suporte a depósitos de correio de voz para trocar caixas de correio somente e não é compatível com sistemas de email O correio de voz na nuvem inclui a transcrição de correio de voz, que é habilitada para todos os usuários da sua organização por padrão. Suas necessidades comerciais podem exigir que você desabilite a transcrição de correio de voz para usuários específicos ou todos em toda a organização.

|Pergunte-se|Ação |
|:------------|:-------|
| Desejo habilitar o correio de voz na nuvem? | Para procedimentos de configuração de correio de voz, consulte [Configurar correio de voz na nuvem](set-up-phone-system-voicemail.md).
| Desejo habilitar a transcrição de correio de voz para alguns ou todos os meus usuários? | Para desativar a transcrição de correio de voz, consulte [definindo políticas de correio de voz em sua organização](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</li></ul>|
|||

### <a name="calling-identity"></a>Identidade de chamada

Por padrão, todas as chamadas de saída usam o número de telefone atribuído como identidade de chamada (identificação de chamadas). O destinatário da chamada pode identificar o autor da chamada rapidamente e decidir se deseja aceitar ou rejeitar a chamada.

|Pergunte-se|Ação |
|:------------|:-------|
|Desejo mascarar ou desabilitar o recurso de identificação de chamadas? | Para alterar ou bloquear a identificação de chamadas, consulte [definir a identificação de chamadas para um usuário](set-the-caller-id-for-a-user.md). |
|||

### <a name="phone-numbers-from-microsoft"></a>Números de telefone da Microsoft

A Microsoft tem dois tipos de números de telefone disponíveis: números de *assinante* (usuário), que podem ser atribuídos a usuários em sua organização e números de *serviço* , disponíveis como chamada de serviço de chamada tarifada e gratuita, que têm uma chamada simultânea maior capacidade do que os números de assinantes e podem ser atribuídos a serviços como conferência de áudio, atendedor automático ou filas de chamadas.

|Pergunte-se|Ação |
| :------------|:-------|
| Quais locais de usuário precisam de novos números de telefone da Microsoft? | Para obter informações sobre como obter números de telefone, consulte [gerenciar números de telefone para sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) e [obter números de telefone para seus usuários](getting-phone-numbers-for-your-users.md). 
| Que tipo de número de telefone (assinante ou serviço) eu preciso? | Para ajudá-lo a escolher o tipo de número de telefone necessário, consulte [diferentes tipos de números de telefone usados para planos de chamadas](different-kinds-of-phone-numbers-used-for-calling-plans.md).
Como faço para portar números de telefone existentes para o Microsoft Teams?|Para obter mais informações, consulte [transferir números de telefone para o Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).
|||

### <a name="dial-plans"></a>Planos de discagem

Um plano de discagem no recurso do sistema de telefonia do Office 365 é um conjunto de regras de normalização que traduz os números de telefone discada em um formato alternativo (geralmente o formato E. 164) para autorização de chamadas e encaminhamento de chamadas.

Para obter mais informações sobre os planos de discagem, confira [O que são os planos de discagem?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

|Pergunte-se|Ação |
|:------------|:-------|
| Minha organização precisa de um plano de discagem personalizado? | Para ajudar a determinar se você precisa de um plano de discagem personalizado, consulte [planejando planos de discagem de locatários](what-are-dial-plans.md#planning-for-tenant-dial-plans)|
Quais usuários exigem um plano de discagem personalizado e qual plano de discagem de locatários deve ser atribuído a cada usuário? | Para adicionar usuários a um plano de discagem personalizado no PowerShell, consulte [criar e gerenciar planos de discagem](create-and-manage-dial-plans.md). |
|||

### <a name="call-queues"></a>Filas de chamadas

As filas de chamadas na nuvem incluem Saudações que são usadas quando alguém liga para um número de telefone para sua organização, a capacidade de colocar automaticamente as chamadas em espera e a capacidade de Pesquisar o próximo agente de chamada disponível para lidar com a chamada enquanto as pessoas que chamam são ouvindo música em espera. Você pode criar uma ou várias filas de chamadas para sua organização. 


|Pergunte-se|Ação |
|:------------|:-------|
| Minha organização precisa de filas de chamadas? | Para obter mais informações, consulte [criar uma fila de chamadas em nuvem](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) e [Configurar o sistema telefônico](setting-up-your-phone-system.md). |

### <a name="auto-attendants"></a>Atendedores automáticos

Os atendedores automáticos na nuvem podem ser usados para criar um sistema de menus para a sua organização que permite que chamadores externos e externos se movimentem por meio de um sistema de menus para localizar e fazer ou transferir chamadas para usuários ou departamentos da empresa em sua organização.

|Pergunte-se|Ação |
|:------------|:-------|
| Minha organização precisa de atendedores automáticos? | Para obter mais informações, consulte [o que são atendedores automáticos da nuvem](what-are-phone-system-auto-attendants.md) e [Configure um atendedor automático na nuvem](create-a-phone-system-auto-attendant.md). |

### <a name="devices"></a>Dispositivos

Para obter mais informações sobre os dispositivos compatíveis, consulte o seguinte:

- [Gerenciar seus dispositivos no Microsoft Teams](device-management.md)
- [Telefones IP](https://docs.microsoft.com/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [Dispositivos de áudio e vídeo USB](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [Comunicações inteligentes para dispositivos](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


