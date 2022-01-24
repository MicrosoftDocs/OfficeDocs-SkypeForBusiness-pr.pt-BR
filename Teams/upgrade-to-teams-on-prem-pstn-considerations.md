---
title: Considerações da PSTN ao atualizar para Teams de Skype for Business
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Considerações sobre voz para atualização de Skype for Business para Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c19c1860c3a351cd7ed6a6240e20dc253f204ab1
ms.sourcegitcommit: bc686eedb37e565148d0c7a61ffa865aaca37d20
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/24/2022
ms.locfileid: "62180884"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a>Considerações do PSTN para atualizar para Teams de Skype for Business local

Este artigo descreve considerações sobre A Rede Telefônica Pública Comutado (PSTN) ao atualizar para Teams.

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

Os artigos a seguir descrevem conceitos de atualização importantes e comportamentos de coexistência:

- [Coexistência de Teams e Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Modos de coexistência - Referência](migration-interop-guidance-for-teams-with-skype.md)
- [Experiência e conformidade do cliente do Teams a modos de coexistência](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > - O Sistema de Telefonia com Teams só é suportado quando a conta do usuário recebe uma política de atualização Teams com o modo Somente Teams.  
 > - O Sistema de Telefonia com Skype for Business só é suportado quando a conta do usuário recebe uma política de atualização Teams com um modo SfB. 
 > - Sistema de Telefonia não é suportado quando a conta do usuário recebe uma política de atualização Teams com o modo Ilhas.
 > - Qualquer encaminhamento de chamada, grupo de chamada de equipe e configurações de delegação de Skype for Business não são migradas e precisarão ser recriadas para Teams.
 > - Para uma visão geral dos Microsoft Teams de voz na nuvem e ajude a decidir qual solução de voz da Microsoft é ideal para sua organização, consulte [Plan your Teams voice solution](cloud-voice-landing-page.md).


## <a name="pstn-calling-scenarios"></a>Cenários de chamada PSTN

Há quatro cenários de chamada possíveis ao se mover para o modo TeamsOnly:

- [Um usuário no Skype for Business Online, com um Plano de Chamada da Microsoft.](#from-skype-for-business-online-with-microsoft-calling-plans) Após a atualização, esse usuário continuará a ter um plano de Chamada da Microsoft.

- [Um usuário no Skype for Business Online,](#from-skype-for-business-online-with-on-premises-voice) com funcionalidade de voz local por meio Skype for Business local ou Cloud Connector Edition. Para garantir que o usuário do TeamsOnly tenha funcionalidade PSTN, você deve coordenar a atualização do usuário para Teams com a migração do usuário para Roteamento Direto.

- [Um usuário em Skype for Business](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)local com Enterprise Voice , que estará mudando para online e mantendo a conectividade PSTN local.  Para migrar esse usuário para Teams, você deve mover a conta de Skype for Business local do usuário para a nuvem e coordenar essa movimentação com a migração do usuário para Roteamento Direto. 

- [Um usuário em Skype for Business local](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)com Enterprise Voice , que estará mudando para online e usando um plano de Chamada da Microsoft.  Para migrar esse usuário para Teams, você deve mover a conta local do usuário Skype for Business para a nuvem. Você deve coordenar a movimentação com A) a porta do número de telefone desse usuário para um Plano de Chamadas da Microsoft ou B) atribuindo um novo número de assinante de regiões disponíveis.

Este artigo fornece apenas uma visão geral de alto nível. Para obter mais informações, [consulte Sistema de Telefonia Direct Routing](direct-routing-landing-page.md) and Calling [Plans](calling-plan-landing-page.md). 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>Do Skype for Business Online com planos de chamada da Microsoft 

Este cenário é o cenário de atualização mais simples envolvendo voz. 

1. Certifique-se de que os usuários tenham sido atribuídos a Teams licença. Por padrão, quando você atribui uma Microsoft 365 ou Office 365, Teams está habilitado. A menos que você tenha desabilitado Teams licença de Teams, nenhuma ação deve ser necessária.

2.  Se os usuários já têm um Plano de Chamadas da Microsoft com um número de telefone, a única alteração necessária é atribuir o modo teamsOnly do usuário no TeamsUpgradePolicy. Antes de atribuir o modo TeamsOnly, as chamadas PSTN de entrada chegarão no cliente Skype for Business usuário. Após a atualização para o modo TeamsOnly, as chamadas PSTN de entrada chegarão no cliente Teams usuário.  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>Do Skype for Business Online com voz local

Nesse cenário, o usuário já está Skype for Business Online. A conectividade PSTN do usuário é local, usando Skype for Business Server modo híbrido ou Cloud Connector Edition. Para migrar esses usuários para o modo TeamsOnly com a funcionalidade PSTN, você deve habilitar os usuários para Roteamento Direto. Com o Roteamento Direto, os troncos PSTN se conectam diretamente ao serviço de Roteamento Direto por meio do SBC (Controlador de Borda de Sessão) local.

As etapas básicas estão listadas abaixo.  As etapas 1-4 são listadas na sequência sugerida, mas podem ser feitas em qualquer ordem. Essas etapas devem ser concluídas antes da Etapa 5.

1. Se você estiver definindo a política de todo o locatário para um dos modos de Skype for Business, certifique-se de criar qualquer usuário de Ilhas existente atribuindo explicitamente o modo Ilhas, conforme descrito anteriormente.

2. Configure seu locatário para Roteamento Direto. Consulte [Resumo da configuração por locatário do Roteamento Direto.](#summary-of-per-tenant-configuration-of-direct-routing)

3. Se desejado, configure várias políticas Teams para esses usuários (por exemplo, TeamsMessagingPolicy, TeamsMeetingPolicy e assim por diante). Você pode configurar as poicies a qualquer momento. No entanto, se você quiser garantir que os usuários tenham a configuração correta quando eles são atualizados, configure essas políticas antes que o usuário seja atualizado para o modo TeamsOnly.

4. Preparar usuários selecionados para migração de voz: 
   - Se necessário, atribua a Teams de usuário.  Supondo que o usuário já está funcional no Skype for Business online local, o usuário já Skype for Business plano 2 e Telefone Microsoft Sistema. Deixe ambos os planos habilitados, incluindo a licença Skype for Business Plano 2 Online.  
   - Atribua o OnlineVoiceRoutingPolicy desejado. 

5. Atualizar o usuário: essas etapas devem ser coordenadas. 

   - Em Microsoft 365 ou Office 365, atualize o usuário para o modo TeamsOnly (Grant-CsTeamsUpgradePolicy).
   - No SBC, configure o roteamento de voz para habilitar chamadas de entrada enviando chamadas para Roteamento Direto, em vez de para o Servidor de Mediação local.


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>De Skype for Business Server local, com Enterprise Voice, para Roteamento Direto

Nesse cenário, o usuário ainda está Skype for Business local. A conectividade PSTN do usuário também é local. Para migrar esse usuário para o modo TeamsOnly com a funcionalidade PSTN, você deve habilitar o usuário para Roteamento Direto e, em seguida, mover o usuário para a nuvem. 
 
As etapas básicas estão listadas abaixo. As etapas 1-5 são listadas na sequência sugerida, mas podem ser feitas em qualquer ordem. Você deve concluir as Etapas 1-5 antes da Etapa 6.

1. Se você estiver definindo a política de todo o locatário para um dos modos de Skype for Business, certifique-se de adoção de usuários de Ilhas existentes atribuindo explicitamente o modo Ilhas, conforme descrito anteriormente.

2. Se você ainda não tiver feito isso, configure a organização para Skype for Business [híbrida](/SkypeForBusiness/hybrid/configure-hybrid-connectivity).

3. Configure seu locatário para Roteamento Direto. Consulte [Resumo da configuração por locatário do Roteamento Direto.](#summary-of-per-tenant-configuration-of-direct-routing)

4. Se desejado, configure várias políticas Teams para esses usuários (por exemplo, TeamsMessagingPolicy, TeamsMeetingPolicy). Você pode configurar políticas a qualquer momento. No entanto, se você quiser garantir que os usuários tenham a configuração correta quando eles são atualizados, configure essas políticas antes que o usuário seja atualizado para o TeamsOnly.

5. Atribua as Microsoft 365 ou Office 365 licenças, se necessário.  O usuário deve ter o Teams e Skype for Business Online 2 e Sistema de Telefonia. Se o Skype for Business Plano Online 2 estiver desabilitado, reabilitar-o.  

6. Atualizar o usuário: essas etapas devem ser coordenadas. 

   - Usando as ferramentas Skype for Business local, execute Move-CsUser com a opção -MoveToTeams. Se você estiver usando uma versão do Skype for Business Server que não dê suporte à opção -MoveToTeams, primeiro execute o Move-CsUser e atribua o modo TeamsOnly no PowerShell remoto do locatário ou no console de administração do Teams.

   - No SBC, configure o roteamento de voz para habilitar chamadas de entrada enviando chamadas para Roteamento Direto, em vez de para o Servidor de Mediação local. 

   - Em Microsoft 365 ou Office 365: Atribua o OnlineVoiceRoutingPolicy relevante para habilitar chamadas de saída. 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>Do Skype for Business Server local, com Enterprise Voice, ao Plano de Chamada da Microsoft

Nesse cenário, o usuário ainda está Skype for Business local. A conectividade PSTN do usuário também é local. Para migrar esse usuário para o modo TeamsOnly com a funcionalidade PSTN, você deve mover o usuário para a nuvem e portar seu número da operadora antiga para um plano de Chamada da Microsoft ou atribuir um novo número ao usuário. 

As etapas básicas estão listadas abaixo.As etapas 1-5 são listadas na sequência sugerida, mas podem ser feitas em qualquer ordem. Você deve concluir as Etapas 1-5 antes da Etapa 6. 

1. Se você estiver definindo a política de todo o locatário para um dos modos de Skype for Business, certifique-se de adoção de usuários de Ilhas existentes atribuindo explicitamente o modo Ilhas, conforme descrito anteriormente. 

2. Se você ainda não tiver feito isso, configure a organização para Skype for Business [híbrida](/SkypeForBusiness/hybrid/configure-hybrid-connectivity). 

3. Se desejado, configure várias políticas Teams para esses usuários (por exemplo, TeamsMessagingPolicy, TeamsMeetingPolicy e assim por diante). Você pode configurar políticas a qualquer momento. No entanto, se você quiser garantir que os usuários tenham a configuração correta quando eles são atualizados, configure essas políticas antes que o usuário seja atualizado para o TeamsOnly. 

4. Atribua as Microsoft 365 ou Office 365 licenças, se necessário.O usuário deve ter o Teams e Skype for Business Online 2 e Sistema de Telefonia. Se o Skype for Business Plano Online 2 estiver desabilitado, reabilitar-o.  

5. Obter números de telefone para seus usuários. (Para obter detalhes, [consulte Manage phone numbers for your organization](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).)

   - Se você estiver reutilizando os números, envie uma solicitação de portação para sua operadora.  
   - Como alternativa, você pode adquirir novos números diretamente da Microsoft. 

6. Atualize o usuário e, se necessário, atribua LineUri. Usando as ferramentas Skype for Business local, execute Move-CsUser com a opção -MoveToTeams.  

    - Se você estiver portando números para a Microsoft, deverá coordenar o momento em que essa operação ocorrerá quando a porta ocorrer. 

    - Se você estiver usando novos números da Microsoft, precisará alterar o LineUri para o usuário depois que o usuário for movido online usando Set-CsPhoneNumberAssignment.  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>Resumo da configuração por locatário do Roteamento Direto 

1. Verifique se o Controlador de Borda de Sessão (SBC) tem suporte com Roteamento Direto, revendo [esta lista](direct-routing-border-controllers.md). Verifique também se você tem a versão correta do firmware.  

2. Emparelhe seu SBC local com o serviço Teams roteamento direto. Para obter detalhes, [consulte Emparelhar o SBC ao serviço de Roteamento Direto de Sistema de Telefonia](direct-routing-configure.md). 

3. Essa configuração é essencialmente um espelho da configuração local. A configuração online consiste em: 
   - OnlineVoiceRoutingPolicy (com base no VoiceRoutingPolicy local se migrar usuários do Skype for Business Online e com base em VoicePolicy se migrar usuários do local com Enterprise Voice).
   - Objetos OnlinePSTNUsage (com base no uso PSTN local). 
   - Objetos OnlineVoiceRoute (com base no VoiceRoute local). 

Para obter mais informações, consulte [Configure Direct Routing](direct-routing-configure.md). 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>Gerenciar a propriedade EnterpriseVoiceEnabled durante a migração 

Seja usando Roteamento Direto ou um plano de Chamadas da Microsoft, um usuário deve ter EnterpriseVoiceEnabled=true no Azure AD para que o usuário tenha funcionalidade PSTN.  EnterpriseVoiceEnabled ("Habilitado para EV") é uma propriedade (não uma política) que existe em um diretório local e na nuvem. O valor na nuvem é o que importa para Teams.  A lógica exata de como a EV habilitada é definida como true depende do seguinte cenário: 

- Se o usuário estiver habilitado para EV no Skype for Business Server local e uma licença Sistema de Telefonia for atribuída ao usuário antes de mover o usuário para a nuvem com Move-CsUser, o usuário online será provisionado com EV-enabled=true. 

- Se um usuário existente do TeamsOnly ou Skype for Business Online tiver uma licença de Sistema de Telefonia, a EV habilitada não será definida como true por padrão. Esse também é o caso se um usuário local for movido para a nuvem antes de atribuir a licença Sistema de Telefonia local. Em ambos os casos, o administrador deve especificar o seguinte cmdlet: 

  ```PowerShell
  Set-CsPhoneNumberAssignment -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a>Links relacionados

[Planejar sua solução Teams voz](cloud-voice-landing-page.md)

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar conectividade híbrida entre Skype for Business Server e Microsoft 365 ou Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover os usuários entre um ambiente local e a nuvem](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usando o Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
