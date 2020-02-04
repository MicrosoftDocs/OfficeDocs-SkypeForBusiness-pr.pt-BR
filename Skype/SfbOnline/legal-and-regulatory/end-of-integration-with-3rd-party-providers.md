---
title: 'Programa de fim de vida útil para a integração do Skype for Business com provedores de serviços de audioconferência de terceiros '
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
localization_priority: None
f1.keywords:
- NOCSH
ms.custom:
- Legal
hideEdit: true
description: Em 31 de julho de 2021, o programa de finalização da vida útil será concluído para a integração do Skype for Business com provedores de serviços de audioconferência de terceiros (ACP de terceiros).
ms.openlocfilehash: b9bd1640d615babab29a073aeeee2b1beb92fc02
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706686"
---
# <a name="end-of-life-program-for-the-integration-of-skype-for-business-with-third-party-audio-conferencing-providers"></a>Programa de fim de vida útil para a integração do Skype for Business com provedores de serviços de audioconferência de terceiros 

A Microsoft anunciou o início do programa de fim de vida útil para a integração do Skype for Business com provedores de serviços de audioconferência (ACPs) de terceiros. 

O programa de fim de vida útil terminará em 31 de julho de 2021. Quando o programa for concluído, a integração do Skype for Business com provedores de audioconferência de terceiros deixará de funcionar, e as seguintes alterações serão observadas na data (31 de julho de 2021):

- Os participantes que tentarem participar de qualquer reunião do Skype for Business por meio de números de discagem fornecidos por um serviço ACP de terceiros não serão mais conectados à reunião do Skype for Business.
 
- Os usuários habilitados para um serviço ACP de terceiros não terão mais suas informações de discagem incluídas automaticamente em todos os novos convites de reunião do Skype for Business.

Como parte do anúncio do início do programa de finalização da vida útil, as seguintes alterações entraram em vigor e continuarão ocorrendo até a conclusão do programa de fim de vida útil: 

- Os clientes sem usuários do Skype for Business configurados para usar um serviço ACP de terceiros não poderão configurar nenhum usuário para usar um serviço ACP terceirizado.

- Os clientes existentes com usuários do Skype for Business configurados para usar um serviço ACP de terceiros continuarão a ser capazes de adicionar novos usuários durante a duração do período de fim da vida útil. Observe que não recomendamos configurar outros usuários do Skype for Business para usar um serviço ACP de terceiros, pois as alterações que entrarão em vigor em 31 de julho de 2021 também se aplicarão a eles.

## <a name="preparing-for-this-change"></a>Preparando-se para essa alteração

Para se preparar para esta mudança, incentivamos as organizações afetadas a notificar os usuários habilitados desta atualização planejada antes de 31 de julho de 2021. 

Após 31 de julho de 2021, os usuários podem continuar a usar o Skype for Business sem nenhuma interrupção nas reuniões online; no entanto, as organizações precisarão habilitar seus usuários para conferências de áudio fornecidas pela Microsoft se exigirem videoconferências discadas com o Skype for Business ou o Microsoft Teams. Para saber mais sobre a conferência de áudio da Microsoft, confira [áudio audioconferência](https://products.office.com/en-us/skype-for-business/audio-conferencing). 

Dependendo do estado final desejado de uma organização, há três caminhos que podem ser seguidos:

- Migrar para a conferência de áudio da Microsoft. 
- Continuar a usar separadamente um provedor de serviços de audioconferência de terceiros. 
- Pare de usar a conferência discada totalmente.

### <a name="path-1-migrate-to-microsoft-audio-conferencing"></a>Caminho #1: migrar para a conferência de áudio da Microsoft   

As organizações que decidem migrar para a conferência de áudio da Microsoft e concluir a migração antes de 31 de julho de 2021 não terão nenhum impacto sobre o serviço durante ou após essa data. A migração para a conferência de áudio da Microsoft apresentará as seguintes alterações em uma organização: 

- O serviço será cobrado com todos os outros serviços do Office 365. 

- Se a assinatura padrão for comprada, o custo de discagem em tarifas será incluído no custo de assinatura mensal por usuário. 

- Um novo conjunto de números de telefone de discagem será fornecido para cada organização e seus usuários. Para ver a cobertura geográfica do serviço de audioconferência da Microsoft, consulte [disponibilidade de país e região para conferências de áudio e planos de chamada](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).
 
- As reuniões que já foram agendadas pelos usuários habilitados com um ACP de terceiros serão automaticamente reagendadas para incluir informações de discagem de conferência do Microsoft Audio.
 
- As IDs de conferência de cada reunião serão dinâmicas, o que significa que cada reunião terá sua própria ID de conferência dedicada. As IDs de conferência dinâmicas fornecem segurança aprimorada e uma experiência aprimorada para reuniões back-to-back.

- Todo o uso do serviço está sujeito aos termos de uso dos serviços de audioconferência. 

Migrar para o Microsoft Audio Conferencing é simples e pode ser feito em apenas algumas etapas após a aquisição das licenças do serviço. Para saber mais sobre como migrar para a conferência de áudio da Microsoft, consulte:

- [Experimentar ou comprar audioconferência no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
 
**Resumo:**

- As organizações que migram para a conferência de áudio da Microsoft e concluírem a migração antes de 31 de julho de 2021, não verão nenhum impacto para o serviço durante ou após essa data.

- Para saber mais sobre como migrar para a conferência de áudio da Microsoft, consulte [experimentar ou comprar videoconferência no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md). 

### <a name="path-2-continue-to-separately-use-a-third-party-audio-conferencing-provider"></a>Caminho #2: continuar a usar separadamente um provedor de audioconferência de terceiros

As organizações que decidem continuar usando um ACP de terceiros em e após 31 de julho de 2021 terão impacto sobre o serviço porque as informações de discagem de ACP de terceiros não poderão mais ser usadas para ingressar na parte de áudio de uma reunião do Skype for Business. 

Para impedir a fragmentação de áudio nas reuniões do Skype for Business com a participação de alguns participantes via VoIP e outros pelo ACP de terceiros, é recomendável que essas organizações desabilitem o uso de VoIP nas reuniões dos usuários. Dessa forma, todos os participantes precisarão ingressar na parte de áudio de uma reunião usando o ACP de terceiros e todas as outras cargas de trabalho da reunião (como chat ou compartilhamento de tela) podem continuar a ser compatíveis com o Skype for Business. 

- Para desabilitar o VoIP de todas as reuniões de um determinado organizador, defina o parâmetro AllowIPAudio de sua política de conferência como falso por meio do cmdlet Set-CsConferencingPolicy. Para obter informações adicionais, consulte [set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
 
Em termos de agendamento e em 31 de julho de 2021, as informações de discagem de um ACP de terceiros não serão mais incluídas automaticamente nos convites de reunião do Skype for Business. Os usuários precisarão adicionar manualmente as informações de discagem em seus convites de reunião do Skype for Business se quiserem continuar incluindo essas informações como parte de suas reuniões. 

Observe que em 31 de julho de 2021, as reuniões existentes dos usuários não serão automaticamente reagendadas para remover qualquer informação de discagem de ACP de terceiros. As organizações que decidem manter o VoIP habilitado para as reuniões de seus usuários devem considerar a desabilitação da integração de ACP de terceiros para seus usuários e reagendar suas reuniões usando o serviço de migração de reunião para remover o áudio de terceiros informações de discagem de conferência a partir de suas reuniões existentes e impedir a fragmentação de áudio em reuniões já agendadas. 

- Para desabilitar a integração de audioconferência de terceiros para um determinado organizador, use o cmdlet Remove-CsUserAcp. Para obter informações adicionais, consulte [Remove-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps). 

- Para reagendar automaticamente as reuniões de usuários após desabilitar a integração com um provedor de serviços de audioconferência de terceiros, consulte "como faço para executar a migração de reunião manualmente para um usuário?" ao [Configurar o serviço de migração de reunião (MMS)](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md). 

**Resumo:**

- As organizações que decidem continuar a usar um ACP de terceiros em e após 31 de julho de 2021 serão afetadas porque um ACP de terceiros não poderá ser usado para ingressar em uma reunião do Skype for Business e as novas reuniões não incluirão informações de discagem de ACP de terceiros. 

- É recomendável que o VoIP seja desabilitado para todas as reuniões de todos os usuários afetados antes de 31 de julho de 2021, para impedir que o áudio seja fragmentado por meio de VoIP e por meio de um ACP terceirizado. 

    - Para desabilitar o VoIP de todas as reuniões de um determinado organizador, defina o parâmetro AllowIPAudio da política de conferência do usuário como falso por meio do cmdlet Set-CsConferencingPolicy. Para obter informações adicionais, consulte [set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
 
- Se uma organização não desabilitar o VoIP para todas as reuniões, é recomendável que os usuários sejam desabilitados usando a integração do Skype for Business online com um ACP terceirizado e reagende suas reuniões para remover as informações de discagem de ACP de terceiros para impedir a fragmentação de áudio.

    - Para desabilitar a integração de audioconferência de terceiros para um determinado organizador, use o cmdlet [Remove-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps) . 

    - Para reagendar automaticamente as reuniões, consulte "como faço para executar a migração de reunião manualmente para um usuário?" ao [Configurar o serviço de migração de reunião (MMS)](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md).

### <a name="path-3-stop-using-dial-in-conferencing-altogether"></a>Caminho #3: parar de usar a conferência discada completamente

As organizações que decidem parar de usar a conferência discada completamente (nenhuma fornecida pela Microsoft nem por um ACP de terceiros) podem depender totalmente do VoIP para dar suporte à parte de áudio de uma reunião do Skype for Business. 

Essas organizações precisariam desabilitar os usuários usando um provedor de serviços de audioconferência de terceiros e ter suas reuniões reagendadas automaticamente usando o serviço de migração de reunião para remover as informações de conferência discada. 

- Para desabilitar a integração de audioconferência de terceiros para um determinado organizador, use o cmdlet Remove-CsUserAcp. Para obter informações adicionais, consulte [Remove-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps). 

- Para reagendar automaticamente as reuniões de usuários após desabilitar a integração com um provedor de serviços de audioconferência de terceiros, consulte "como faço para executar a migração de reunião manualmente para um usuário?" ao [Configurar o serviço de migração de reunião (MMS)](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md). 

**Resumo:** 

- As organizações que decidem parar de usar a conferência de áudio completamente antes de 31 de julho de 2021 não serão afetadas.

- Para desabilitar a integração de audioconferência de terceiros para um determinado organizador, use o cmdlet Remove-CsUserAcp. Para obter informações adicionais, consulte [Remove-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/remove-csuseracp?view=skype-ps). 

- Para reagendar automaticamente as reuniões de usuários após desabilitar a integração com provedores de audioconferência de terceiros, consulte "como faço para executar a migração de reunião manualmente para um usuário?" ao [Configurar o serviço de migração de reunião (MMS)](../audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md).
