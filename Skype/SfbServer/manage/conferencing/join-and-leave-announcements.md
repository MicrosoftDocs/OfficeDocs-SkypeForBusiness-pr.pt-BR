---
title: Gerenciar anúncios de união e saída de conferências no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 'Resumo: saiba como gerenciar anúncios de união e saída de conferências no Skype for Business Server.'
ms.openlocfilehash: 796266dd3b571e525f657d5dbe712d1577779cae
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119450"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>Gerenciar anúncios de união e saída de conferências no Skype for Business Server
 
**Resumo:** Saiba como gerenciar anúncios de junção e saída de conferências no Skype for Business Server.
  
Quando os usuários discados inserem ou saem de uma conferência, o aplicativo Comunicado de Conferência pode anunciar sua entrada ou saída tocando um tom ou dizendo seus nomes. Você pode alterar como os anúncios funcionam usando o Shell de Gerenciamento do Skype for Business Server e o cmdlet **Set-CsDialinConferencing** com os seguintes parâmetros:
  
- EnableNameRecording - Determina se os participantes anônimos são solicitados a gravar seu nome antes de entrar na conferência. O valor padrão é "$true", que significa que os participantes receberão essa solicitação. (Os participantes autenticados não registram seus nomes, pois em vez disso exibem seus nomes de exibição.)
    
- EntryExitAnnouncementsEnabledByDefault - Indica se os anúncios estão ativas ou desligadas por padrão. O valor padrão é "$false", que significa que, por padrão, não anúncios quando os participantes ingressam ou saem de uma conferência. O organizador da reunião pode substituir essa configuração ao agendar uma reunião.
    
- EntryExitAnnouncementsType - Indica a ação tomada sempre que um participante insue ou saia de uma conferência para a qual os comunicados estão habilitados. O valor padrão é "UseNames", que significa que há um anúncio parecido com o seguinte: "Ken Myer ingressou na conferência" quando os anúncios estão ativados.
    
É possível definir essas configurações no escopo global ou no escopo do site. As configurações definidas no escopo do site têm precedência sobre as configurações definidas no escopo global.
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>Para modificar o comportamento de anúncio de ingresso e saída de conferência

1. Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função Cs-ServerAdministrator ou CsAdministrator.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** em **Skype for Business 2015** e em Shell de Gerenciamento do **Skype for Business Server.**
    
3. Execute o seguinte no prompt de comando:
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

Este cmdlet recupera informações sobre se os participantes devem registrar seu nome ao ingressar em uma conferência e como o Skype for Business Server responde quando os participantes inserem ou saem de uma conferência discada.
    
4. Execute o seguinte no prompt de comando:
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

No exemplo a seguir, as configurações são configuradas no escopo do site para Redmond. Os anúncios estão ativados, mas os participantes não recebem uma solicitação para inserir seus nomes quando ingressam em uma conferência. Um tom é tocado quando os participantes entram ou saem de uma conferência:
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

Para obter mais informações, incluindo sintaxe e uma lista completa de parâmetros, consulte [Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).
