---
title: Nuvem de voz no Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
description: Página de aterrissagem à implantação de voz de nuvem em equipes
appliesto:
- Microsoft Teams
ms.openlocfilehash: 969bab316a39ec873fea802a9c257cf062891bb9
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/01/2019
ms.locfileid: "30351294"
---
# <a name="cloud-voice-in-microsoft-teams"></a>Nuvem de voz no Microsoft Teams

Você concluiu a [Introdução](get-started-with-teams-quick-start.md). Você implementou o Teams com [chat, equipes, canais e aplicativos](deploy-chat-teams-channels-microsoft-teams-landing-page.md) na organização. Talvez você implantou [conferência de & de reuniões](deploy-meetings-microsoft-teams-landing-page.md). Agora você está pronto para adicionar recursos de voz de nuvem para seus usuários. 

Voz nuvem oferece recursos de Private Branch Exchange (PBX) e as opções para conectar-se para a comutação telefônica PSTN (rede pública).

Este artigo ajuda você a decidir se você precisa alterar as configurações de voz da nuvem padrão, com base no perfil da sua organização e requisitos de negócios, e em seguida, ele o orienta durante cada alteração. Podemos ter dividir as configurações em dois grupos, começando com o conjunto básico de [alterações que estão mais provável fazer](#core-deployment-decisions). O segundo grupo inclui [configurações adicionais](#additional-deployment-decisions) que poderão ser configuradas com base nas necessidades da organização.

É recomendável que todas as organizações for percorrendo as decisões de núcleo e em seguida, se sua organização tiver requisitos adicionais, examine o material a seguir.



## <a name="learn-more-about-cloud-voice"></a>Saiba mais sobre voz de nuvem

Os artigos a seguir fornecem mais informações sobre a implantação e uso de recursos de voz de nuvem em equipes:

- [Sistema de Telefonia no Office 365](what-is-phone-system-in-office-365.md)
- [Sistema telefônico com a chamada de plano](calling-plan-landing-page.md)
- [Roteamento direto de sistema do telefone](direct-routing-landing-page.md)
- [Implantação do Cloud Voice](cloud-voice-deployment.md)
- [Soluções de telefonia da Microsoft](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)
- Assista a sessão a seguir para saber mais sobre o sistema telefônico: [Introdução ao sistema de telefone em equipes da Microsoft](https://aka.ms/teams-phone-system)


## <a name="core-deployment-decisions"></a>Decisões importantes sobre implantação

Estas são as configurações que a maioria das organizações deseja alterar (se as configurações padrão do Teams não atenderem às necessidades da organização).

## <a name="phone-system-office-365"></a>Sistema telefônico (Office 365)

Sistema telefônico é uma tecnologia da Microsoft para habilitar o controle de chamada e os recursos na nuvem do Office 365 Private Branch Exchange (PBX). Sistema telefônico permite que você substitua o seu sistema Private Branch Exchange (PBX) existente um conjunto de recursos entregues diretamente do Office 365 e estreitamente integrado ao experiência de produtividade de nuvem da empresa.


|Pergunte a si mesmo|Ação |
|:------------|:-------|
|Em que os locais do usuário ou escritórios eu implementará sistema telefônico? |Para obter mais informações sobre o sistema telefônico, consulte [o que é o sistema telefônico no Office 365](what-is-phone-system-in-office-365.md).</li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a>A Conexão ao público Switched Telephone Network (PSTN)

Para conectar o sistema telefônico para a comutação telefônica PSTN (rede pública) para que os usuários podem fazer chamadas telefônicas em todo o mundo, você tem opções com base em suas necessidades comerciais.  Pergunte-se o seguinte:


|Pergunte a si mesmo|Ação |
| :------------|:-------|
| Você deseja usar o Microsoft chamar planejar como minha operadora de telefonia? | Para obter mais informações, consulte [Sistema telefônico com planos de chamada](calling-plan-landing-page.md).|
| É necessário usar meu próprios operadora de telefonia? | Para obter mais informações, consulte [Sistema telefônico com o roteamento direto](direct-routing-landing-page.md).
|||


## <a name="additional-deployment-decisions"></a>Decisões adicionais de implantação

Talvez você queira alterar as configurações para o seguinte, com base nas necessidades e a configuração da sua organização:

- Caixa postal
- Identificação de chamadas
- Números de telefone da Microsoft
- Planos de discagem
- Filas de chamadas
- Atendedores automáticos

### <a name="voicemail"></a>Caixa postal

Caixa postal de sistema telefônico, possibilitada pela serviços de caixa postal do Azure, suporta depósitos de correio de voz em somente caixas postais do Exchange e não oferece suporte a sistemas de email de terceiros. A caixa postal do Sistema de Telefonia inclui transcrição da caixa postal que, por padrão, está habilitada para todos os usuários da organização. Suas necessidades de negócios podem exigir que você desative as transcrições de caixa postal para usuários específicos ou todos em toda a organização.

|Pergunte a si mesmo|Ação |
|:------------|:-------|
| Você deseja habilitar a caixa postal de sistema telefônico? | Para obter procedimentos de instalação de caixa postal, consulte [Configure a caixa postal do sistema telefônico](set-up-phone-system-voicemail.md).
| Você deseja habilitar a transcrição do correio de voz para alguns ou todos os meus usuários? | Para desativar a transcrição do correio de voz, consulte [definir políticas de caixa postal na sua organização](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</li></ul>|
|||

### <a name="calling-identity"></a>Identificação de chamadas

Por padrão, todas as chamadas de saída usam o número de telefone atribuído como identidade de chamada (ID de chamador). O destinatário da chamada pode identificar o autor da chamada rapidamente e decidir se deseja aceitar ou rejeitar a chamada.

|Pergunte a si mesmo|Ação |
|:------------|:-------|
|Eu quiser mascarar ou desabilitar o ID do chamador? | Para alterar ou bloquear a ID do chamador, consulte [definir a identificação do chamador para um usuário](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user). |
|||

### <a name="phone-numbers-from-microsoft"></a>Números de telefone da Microsoft

A Microsoft tem dois tipos de números de telefone disponíveis: números de *telefone do assinante* (usuário), que podem ser atribuídos aos usuários em sua organização e números de *serviço* , disponíveis como Chamada Tarifada e números gratuitos de serviço, que possuem chamada simultânea superior capacidade que os números de telefone do assinante e podem ser atribuídas aos serviços, como a conferência de áudio, atendedores automáticos ou chamada filas.

|Pergunte a si mesmo|Ação |
| :------------|:-------|
| Quais locais do usuário precisam novos números de telefone da Microsoft? | Para obter informações sobre a obtenção de números de telefone, consulte [gerenciar números de telefone para sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) e [os números de telefone de Introdução para seus usuários](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users). 
| Qual tipo de número de telefone (assinante ou serviço) precisa? | Para ajudá-lo a escolher o tipo de número de telefone que você precisa, consulte [tipos diferentes de números de telefone usados para chamar planos](different-kinds-of-phone-numbers-used-for-calling-plans.md).
Como faço para números de telefone existente do porta para o Office 365?|Para obter mais informações, consulte [transferir os números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md).
|||

### <a name="dial-plans"></a>Planos de discagem

Um plano de discagem no recurso de sistema telefônico do Office 365 é um conjunto de regras de normalização convertem discado números de telefone em um formato alternativo (normalmente o formato e. 164) para autorização de chamada e roteamento de chamada.

Para obter mais informações sobre os planos de discagem, confira [O que são os planos de discagem?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

|Pergunte-se|Ação |
|:------------|:-------|
| Minha organização precisa de um plano de discagem personalizado? | Para ajudar a determinar se você precisa de um plano de discagem personalizado, consulte [Planejando locatário planos de discagem](what-are-dial-plans.md#planning-for-tenant-dial-plans)|
Quais usuários exigem um plano de discagem personalizado e qual plano de discagem de locatários deve ser atribuído a cada usuário? | Para adicionar usuários a um plano de discagem personalizada no PowerShell, consulte [criar e gerenciar planos de discagem](create-and-manage-dial-plans.md). |
|||

### <a name="call-queues"></a>Filas de chamadas

Telefonema de sistema filas incluem saudações que são usadas quando alguém chama um número de telefone para sua organização, a capacidade de colocar automaticamente as chamadas em espera e a capacidade de pesquisar para o próximo operador chamada disponíveis lidar com a chamada enquanto as pessoas que chamada está escutando a música em espera. Você pode criar uma fila de chamadas única ou múltiplas para a sua organização. 


|Pergunte a si mesmo|Ação |
|:------------|:-------|
| Minha organização precisa chama filas? | Para obter mais informações, consulte [criar uma fila de espera de chamada de sistema telefônico](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) e a [configuração do seu sistema telefônico](setting-up-your-phone-system.md). |

### <a name="auto-attendants"></a>Atendedores automáticos

Sistema telefônico atendedores automáticos podem ser usados para criar um sistema de menu para a sua organização que permite que os chamadores externos e internos mover através de um sistema de menu localizar e colocar ou transferir chamadas para usuários da empresa ou departamentos na organização.

|Pergunte a si mesmo|Ação |
|:------------|:-------|
| Minha organização precisa de atendedores automáticos? | Para obter mais informações, consulte [Cite atendedores automáticos de sistema telefônico](what-are-phone-system-auto-attendants.md) e [Configurar um atendedor automático de sistema telefônico](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json). |

### <a name="devices"></a>Dispositivos

Para obter mais informações sobre os dispositivos suportados, consulte o seguinte:

- [Gerenciar seus dispositivos no Microsoft Teams](device-management.md)
- [Telefones IP](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [Dispositivos de áudio e vídeos USB](https://docs.microsoft.com/en-us/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [Comunicações inteligentes para dispositivos](https://products.office.com/en-gb/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


