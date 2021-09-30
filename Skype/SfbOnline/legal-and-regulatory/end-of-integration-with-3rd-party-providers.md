---
title: 'Programa de fim de vida para a integração de Skype for Business com provedores de audioconferência de terceiros '
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: article
ms.assetid: dc6e95cd-51e8-49ca-bcd3-78dc9dae486a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: ''
f1.keywords:
- NOCSH
ms.custom:
- Legal
hideEdit: true
description: Em 31 de julho de 2021, o programa de fim de vida concluirá a integração do Skype for Business com provedores de audioconferência de terceiros (ACP de terceiros).
ms.openlocfilehash: c159d201a284b683237df22688878ef268c442b1
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014375"
---
# <a name="end-of-life-program-for-the-integration-of-skype-for-business-with-third-party-audio-conferencing-providers"></a>Programa de fim de vida para a integração de Skype for Business com provedores de audioconferência de terceiros 

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

A Microsoft anuncia o início do programa de fim de vida para a integração de Skype for Business com provedores de audioconferência de terceiros (ACPs). 

O programa de fim de vida será concluído em 31 de julho de 2021. Quando o programa for concluído, a integração do Skype for Business com provedores de audioconferência de terceiros irá parar de funcionar e as seguintes alterações serão observadas nessa data (31 de julho de 2021):

- Os participantes que tentarem ingressar em qualquer reunião Skype for Business por meio de números de discagem fornecidos por um serviço ACP de terceiros não serão mais conectados à reunião Skype for Business de terceiros.
 
- Os usuários habilitados para um serviço ACP de terceiros não terão mais suas informações de discagem automaticamente incluídas em quaisquer novos convites de Skype for Business de reunião.

Como parte do anúncio do início do programa de fim de vida, as seguintes alterações entraram em vigor e continuarão em vigor até a conclusão do programa de fim de vida: 

- Os clientes sem Skype for Business configurados para usar um serviço ACP de terceiros não poderão configurar nenhum usuário para usar um serviço ACP de terceiros.

- Os clientes existentes com Skype for Business configurados para usar um serviço ACP de terceiros continuarão a adicionar novos usuários durante o período de fim de vida. Observe que não recomendamos configurar usuários adicionais Skype for Business usar um serviço ACP de terceiros, pois as alterações que entrarão em vigor em 31 de julho de 2021 também serão aplicadas a eles.

## <a name="preparing-for-this-change"></a>Preparando-se para essa mudança

Para se preparar para essa alteração, incentivamos as organizações afetadas a notificar seus usuários habilitados sobre essa atualização planejada antes de 31 de julho de 2021. 

Após 31 de julho de 2021, os usuários podem continuar a usar Skype for Business sem interrupção em suas reuniões online; no entanto, as organizações precisarão habilitar seus usuários para Audioconferência fornecidas pela Microsoft se exigirem audioconferência discada com Skype for Business ou Microsoft Teams. Para saber mais sobre a Audioconferência da Microsoft, consulte [audioconferência](https://www.microsoft.com/microsoft-teams/audio-conferencing). 

Dependendo do estado final desejado de uma organização, há três caminhos que podem ser seguidos:

- Migrar para a Audioconferência da Microsoft. 
- Continue a usar separadamente um provedor de audioconferência de terceiros. 
- Pare de usar a conferência discado completamente.

### <a name="path-1-migrate-to-microsoft-audio-conferencing"></a>Caminho #1: Migrar para a Audioconferência da Microsoft   

As organizações que decidirem migrar para a Audioconferência da Microsoft e concluir sua migração antes de 31 de julho de 2021, não terão impacto no serviço durante ou após essa data. A migração para a Audioconferência da Microsoft apresentará as seguintes alterações em uma organização: 

- O serviço será cobrado com todos os outros Microsoft 365 ou Office 365 serviços. 

- Se a assinatura padrão for comprada, o custo de discagem por telefone será incluído no custo mensal da assinatura por usuário. 

- Um novo conjunto de números de telefone discados será fornecido para cada organização e seus usuários. Para ver a cobertura geográfica do serviço de Audioconferência da Microsoft, consulte Disponibilidade de país e [região para Planos de Audioconferência e Chamada.](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
 
- As reuniões que já foram agendadas por usuários habilitados com um ACP de terceiros serão reagendadas automaticamente para incluir informações de discagem de Audioconferência da Microsoft.
 
- As IDs de conferência de cada reunião serão dinâmicas, o que significa que cada reunião terá sua própria ID de conferência dedicada. As IDs de conferência dinâmica fornecem segurança aprimorada e uma experiência aprimorada para reuniões back-to-back.

- Todo o uso do serviço está sujeito aos termos de uso dos serviços de Audioconferência. 

Migrar para a Audioconferência da Microsoft é simples e pode ser feito em apenas algumas etapas após a aquisição das licenças do serviço. Para saber mais sobre como migrar para a Audioconferência da Microsoft, consulte:

- [Experimente ou compre Audioconferência em Microsoft 365 ou Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
 
**Resumo:**

- As organizações que migram para a Audioconferência da Microsoft e concluem a migração antes de 31 de julho de 2021 não verão qualquer impacto no serviço durante ou após essa data.

- Para saber mais sobre como migrar para a Audioconferência da Microsoft, consulte [Try or purchase Audio Conferencing in Microsoft 365 or Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md). 

### <a name="path-2-continue-to-separately-use-a-third-party-audio-conferencing-provider"></a>Caminho #2: continuar a usar separadamente um provedor de audioconferência de terceiros

As organizações que decidirem continuar usando um ACP de terceiros em e após 31 de julho de 2021 terão impacto no serviço porque as informações de discagem ACP de terceiros não poderão mais ser usadas para ingressar na parte de áudio de uma reunião Skype for Business de terceiros. 

Para evitar a fragmentação de áudio em reuniões Skype for Business, fazendo com que alguns participantes participem via VoIP e outros por meio do ACP de terceiros, é recomendável que essas organizações desabilitem o uso de VoIP nas reuniões de seus usuários. Dessa forma, todos os participantes precisarão ingressar na parte de áudio de uma reunião usando o ACP de terceiros e todas as outras cargas de trabalho da reunião (como chat ou compartilhamento de tela) podem continuar a ser suportadas por meio de Skype for Business. 

- Para desabilitar VoIP de todas as reuniões de um determinado organizador, defina o parâmetro AllowIPAudio de sua Política de Conferência como false por meio do cmdlet Set-CsConferencingPolicy. Para obter informações adicionais, [consulte Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
 
Em termos de agendamento, e a partir de 31 de julho de 2021, as informações de discagem de um ACP de terceiros não serão mais incluídas automaticamente nos convites de reunião Skype for Business de reunião. Os usuários precisarão adicionar manualmente as informações de discagem em seus convites de reunião Skype for Business se desejarem continuar incluindo essas informações como parte de suas reuniões. 

Observe que, em 31 de julho de 2021, as reuniões de usuários existentes não serão reagendadas automaticamente para remover qualquer informação de discagem ACP de terceiros. As organizações que decidem manter o VoIP habilitado para as reuniões de seus usuários devem considerar desabilitar a integração de ACP de terceiros para seus usuários e reagendar suas reuniões usando o serviço de migração de reunião para remover as informações de discagem de audioconferência de terceiros de suas reuniões existentes e impedir a fragmentação de áudio em reuniões já agendadas. 

- Para desabilitar a integração da audioconferência de terceiros para um determinado organizador, use o cmdlet Remove-CsUserAcp de terceiros. Para obter informações adicionais, [consulte Remove-CsUserAcp](/powershell/module/skype/remove-csuseracp?view=skype-ps). 

- Para reagendar automaticamente as reuniões de usuários após desabilitar a integração com um provedor de audioconferência de terceiros, consulte "Como executar a Migração de Reunião manualmente para um usuário?" em [Configurando o Serviço de Migração de Reunião (MMS)](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md). 

**Resumo:**

- As organizações que decidirem continuar usando um ACP de terceiros em e após 31 de julho de 2021 serão afetadas porque um ACP de terceiros não poderá ser usado para ingressar em uma reunião do Skype for Business e novas reuniões não incluirão informações de discagem ACP de terceiros. 

- É recomendável que o VoIP seja desabilitado para todas as reuniões de todos os usuários afetados antes de 31 de julho de 2021, para evitar que o áudio seja fragmentado entre os participantes que ingressarem via VoIP e por meio de um ACP de terceiros. 

    - Para desabilitar VoIP de todas as reuniões de um determinado organizador, defina o parâmetro AllowIPAudio da Política de Conferência do usuário como false por meio do cmdlet Set-CsConferencingPolicy. Para obter informações adicionais, [consulte Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
 
- Se uma organização não desabilitar o VoIP para todas as reuniões, é recomendável que os usuários sejam desabilitados de usar a integração do Skype for Business Online com um ACP de terceiros e reagendar suas reuniões para remover as informações de discagem ACP de terceiros para evitar a fragmentação do áudio.

    - Para desabilitar a integração da audioconferência de terceiros para um determinado organizador, use o cmdlet [Remove-CsUserAcp.](/powershell/module/skype/remove-csuseracp?view=skype-ps) 

    - Para reagendar automaticamente as reuniões, consulte "Como executar a Migração de Reunião manualmente para um usuário?" em [Configurando o Serviço de Migração de Reunião (MMS)](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md).

### <a name="path-3-stop-using-dial-in-conferencing-altogether"></a>Caminho #3: pare de usar a conferência discagem completamente

As organizações que decidem parar de usar a conferência discada completamente (nem fornecida pela Microsoft nem por um ACP de terceiros) podem contar totalmente com o VoIP para dar suporte à parte de áudio de uma reunião Skype for Business de terceiros. 

Essas organizações precisariam desabilitar seus usuários de usar um provedor de audioconferência de terceiros e remarcar automaticamente suas reuniões usando o serviço de migração de reunião para remover suas informações de conferência discada. 

- Para desabilitar a integração da audioconferência de terceiros para um determinado organizador, use o cmdlet Remove-CsUserAcp de terceiros. Para obter informações adicionais, [consulte Remove-CsUserAcp](/powershell/module/skype/remove-csuseracp?view=skype-ps). 

- Para reagendar automaticamente as reuniões de usuários após desabilitar a integração com um provedor de audioconferência de terceiros, consulte "Como executar a Migração de Reunião manualmente para um usuário?" em [Configurando o Serviço de Migração de Reunião (MMS)](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md). 

**Resumo:** 

- As organizações que decidirem parar de usar a audioconferência completamente antes de 31 de julho de 2021 não serão impactadas.

- Para desabilitar a integração da audioconferência de terceiros para um determinado organizador, use o cmdlet Remove-CsUserAcp de terceiros. Para obter informações adicionais, [consulte Remove-CsUserAcp](/powershell/module/skype/remove-csuseracp?view=skype-ps). 

- Para reagendar automaticamente as reuniões de usuários após desabilitar a integração com provedores de audioconferência de terceiros, consulte "Como executar a Migração de Reunião manualmente para um usuário?" em [Configurando o Serviço de Migração de Reunião (MMS)](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md).
