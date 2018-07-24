---
title: Gerenciar o ingresso na conferência e deixar anúncios em Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 'Resumo: Saiba como gerenciar o ingresso na conferência e deixar anúncios em Skype para Business Server.'
ms.openlocfilehash: 84c9b5f9457d16570e58b119329d6b8fcefa4205
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21008488"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>Gerenciar o ingresso na conferência e deixar anúncios em Skype para Business Server
 
**Resumo:** Saiba como gerenciar o ingresso na conferência e deixar anúncios em Skype para Business Server.
  
Quando os usuários discados ingressar ou sair de uma conferência, o aplicativo de anúncio de conferência pode anunciar seu entrada ou saia por reproduzir um tom ou dizendo seus nomes. Você pode alterar como os anúncios funcionam usando Skype para o Shell de gerenciamento de servidor de negócios e o cmdlet **Set-CsDialinConferencing** com os seguintes parâmetros:
  
- EnableNameRecording  - Determina se os participantes anônimos devem receber uma solicitação para registrar seus nomes antes de entrar na conferência. O valor padrão é "$true", que significa que os participantes receberão essa solicitação. (Os participantes autenticados não registram seus nomes porque seu nome de exibição é utilizado.)
    
- EntryExitAnnouncementsEnabledByDefault - Indica se os anúncios estão ativados ou desativados por padrão. O valor padrão é "$false", o que significa que, por padrão, não há anúncios quando os participantes participam ou saem de uma conferência. O organizador da reunião pode substituir essa configuração ao agendar uma reunião.
    
- EntryExitAnnouncementsType - Indica a ação a ser executada sempre que um participante participa ou sai de uma conferência para a qual os anúncios estão habilitados. O valor padrão é "UseNames", que significa que há um anúncio parecido com o seguinte: "Ken Myer está participando da conferência" quando os anúncios são ativados.
    
É possível definir essas configurações no escopo global ou no escopo do site. As configurações definidas no escopo do site têm precedência sobre as configurações definidas no escopo global.
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>Para modificar o comportamento de anúncio de ingresso e saída de conferência

1. Faça logon no computador como membro do grupo  RTCUniversalServerAdmins  ou como membro da função  Cs-ServerAdministrator  ou  CsAdministrator.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Execute o seguinte no prompt de comando:
    
  ```
  Get-CsDialinConferencingConfiguration
  ```

Este cmdlet recupera informações sobre se os participantes precisarão registrar seus nomes ao ingressar em uma conferência e como o Skype para Business Server responde quando os participantes ingressam ou saem de uma conferência discada.
    
4. Execute o seguinte no prompt de comando:
    
  ```
  Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
[-EnableNameRecording <$true | $false>]
[-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
[-EntryExitAnnouncementsType <UseNames | ToneOnly]
  ```

Neste exemplo, as configurações estão definidas no escopo do site para Redmond. Os anúncios estão ativados, mas os participantes não recebem uma solicitação para inserir seus nomes quando ingressam em uma conferência. Um tom é reproduzido quando os participantes entram e saem de uma conferência.
  
```
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

Para obter mais informações, incluindo a sintaxe e uma lista completa de parâmetros, consulte [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).
  

