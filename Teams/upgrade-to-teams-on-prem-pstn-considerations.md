---
title: Considerações sobre PSTN ao atualizar para Teams do Skype for Business
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Considerações de voz para atualização Skype for Business para Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 130ff6164de3cae82902487f70dd6eaefb631c27
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681342"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a>Considerações sobre PSTN para atualizar para Teams do Skype for Business local

Este artigo descreve as considerações da Rede Telefônica Pública Comunada (PSTN) ao atualizar para Teams.

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

Os artigos a seguir descrevem conceitos importantes de atualização e comportamentos de coexistência:

- [Coexistência de Teams e Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Modos de coexistência – Referência](migration-interop-guidance-for-teams-with-skype.md)
- [Experiência e conformidade do cliente do Teams a modos de coexistência](teams-client-experience-and-conformance-to-coexistence-modes.md)

> [!NOTE]
>
> - O Sistema de Telefonia com Teams só tem suporte quando a conta do usuário recebe uma política de atualização Teams com o modo somente Teams usuário.
> - O Sistema de Telefonia com Skype for Business só tem suporte quando a conta do usuário recebe uma política Teams atualização com um modo SfB.
> - Sistema de Telefonia não é compatível quando a conta do usuário recebe uma política Teams atualização com o modo Ilhas.
> - Qualquer encaminhamento de chamadas, grupo de chamadas de equipe e configurações de delegação do Skype for Business não são migrados e precisarão ser recriados para Teams.
> - Para obter uma visão geral dos Microsoft Teams de voz na nuvem e ajudar a decidir qual solução de voz da Microsoft é ideal para sua organização, consulte Planejar sua [Teams voz](cloud-voice-landing-page.md).

## <a name="pstn-calling-scenarios"></a>Cenários de chamada PSTN

Há quatro cenários de chamada possíveis ao migrar para o modo TeamsOnly:

- [Um usuário do Skype for Business Online, com um Plano de Chamadas da Microsoft](#from-skype-for-business-online-with-microsoft-calling-plans). Após a atualização, esse usuário continuará a ter um plano de Chamada da Microsoft.

- [Um usuário do Skype for Business Online,](#from-skype-for-business-online-with-on-premises-voice) com funcionalidade de voz local por meio Skype for Business local ou Cloud Connector Edition. Para garantir que o usuário do TeamsOnly tenha a funcionalidade PSTN, você deve coordenar a atualização do usuário para o Teams com a migração do usuário para o Roteamento Direto.

- [Um usuário Skype for Business local](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing) com Enterprise Voice, que será movido para online e manterá a conectividade PSTN local.  Para migrar esse usuário para o Teams, você deve mover a conta de Skype for Business local do usuário para a nuvem e coordenar isso com a migração do usuário para o Roteamento Direto.

- [Um usuário em Skype for Business local com o Enterprise Voice](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), que será migrado para online e usando um plano de Chamada da Microsoft.  Para migrar esse usuário para Teams, você deve mover a conta de Skype for Business local do usuário para a nuvem. Você deve coordenar a movimentação com A) a porta do número de telefone desse usuário para um Plano de Chamada da Microsoft ou B) atribuindo um novo número de assinante de regiões disponíveis.

Este artigo fornece apenas uma visão geral de alto nível. Para obter mais informações, [consulte Sistema de Telefonia roteamento direto](direct-routing-landing-page.md) e [planos de chamada](calling-plan-landing-page.md).

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>Do Skype for Business Online com planos de chamadas da Microsoft

Esse cenário é o cenário de atualização mais simples que envolve voz.

1. Verifique se os usuários foram atribuídos a Teams licença. Por padrão, quando você atribui uma licença Microsoft 365 ou Office 365, Teams é habilitada. A menos que você tenha desabilitado a Teams, nenhuma ação deve ser necessária.

2. Se os usuários já tiverem um Plano de Chamadas da Microsoft com um número de telefone, a única alteração necessária será atribuir o modo TeamsOnly do usuário no TeamsUpgradePolicy. Antes de atribuir o modo TeamsOnly, as chamadas PSTN de entrada chegarão ao cliente Skype for Business usuário. Após a atualização para o modo TeamsOnly, as chamadas PSTN de entrada chegarão ao cliente Teams usuário.

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>Do Skype for Business Online com voz local

Nesse cenário, o usuário já está no Skype for Business Online. A conectividade PSTN do usuário é local, usando Skype for Business Server modo híbrido ou Cloud Connector Edition. Para migrar esses usuários para o modo TeamsOnly com a funcionalidade PSTN, você deve habilitar os usuários para Roteamento Direto. Com o Roteamento Direto, os troncos PSTN se conectam diretamente ao serviço de Roteamento Direto por meio do SBC (Controlador de Borda de Sessão) local.

As etapas básicas estão listadas abaixo.  As etapas 1 a 4 são listadas na sequência sugerida, mas podem ser feitas em qualquer ordem. Essas etapas devem ser concluídas antes da Etapa 5.

1. Se você estiver definindo a política em todo o locatário para um dos modos Skype for Business, certifique-se de avôr quaisquer usuários existentes das Ilhas atribuindo explicitamente o modo Ilhas, conforme descrito anteriormente.

2. Configure seu locatário para Roteamento Direto. Consulte [Resumo da configuração por locatário do Roteamento Direto](#summary-of-per-tenant-configuration-of-direct-routing).

3. Se desejar, configure várias Teams para esses usuários (por exemplo, TeamsMessagingPolicy, TeamsMeetingPolicy e assim por diante). Você pode configurar as políticas a qualquer momento. No entanto, se você quiser garantir que os usuários tenham a configuração correta quando forem atualizados, configure essas políticas antes que o usuário seja atualizado para o modo TeamsOnly.

4. Preparar usuários selecionados para migração de voz:
   - Se necessário, atribua a Teams licença.  Supondo que o usuário já esteja funcional Skype for Business voz local online, o usuário já tem Skype for Business Plano 2 e Telefone Microsoft Sistema. Deixe ambos os planos habilitados, incluindo a licença Skype for Business Online Plano 2.
   - Atribua o OnlineVoiceRoutingPolicy desejado.

5. Atualizar o usuário: essas etapas devem ser coordenadas.

   - No Microsoft 365 ou Office 365, atualize o usuário para o modo TeamsOnly (Grant-CsTeamsUpgradePolicy).
   - No SBC, configure o roteamento de voz para habilitar chamadas de entrada enviando chamadas para Roteamento Direto em vez de para o Servidor de Mediação local.

## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>Do Skype for Business Server local, com o Enterprise Voice, para o Roteamento Direto

Nesse cenário, o usuário ainda está hospedado Skype for Business local. A conectividade PSTN do usuário também é local. Para migrar esse usuário para o modo TeamsOnly com a funcionalidade PSTN, você deve habilitar o usuário para Roteamento Direto e, em seguida, mover o usuário para a nuvem.

As etapas básicas estão listadas abaixo. As etapas 1 a 5 são listadas na sequência sugerida, mas podem ser feitas em qualquer ordem. Você deve concluir as Etapas 1 a 5 antes da Etapa 6.

1. Se você definir a política em todo o locatário para um dos modos Skype for Business, certifique-se de avôr usuários existentes das Ilhas atribuindo explicitamente o modo Ilhas, conforme descrito anteriormente.

2. Se você ainda não fez isso, [configure a organização para Skype for Business híbrido](/SkypeForBusiness/hybrid/configure-hybrid-connectivity).

3. Configure seu locatário para Roteamento Direto. Consulte [Resumo da configuração por locatário do Roteamento Direto](#summary-of-per-tenant-configuration-of-direct-routing).

4. Se desejar, configure várias Teams para esses usuários (por exemplo, TeamsMessagingPolicy, TeamsMeetingPolicy). Você pode configurar políticas a qualquer momento. No entanto, se você quiser garantir que os usuários tenham a configuração correta quando forem atualizados, configure essas políticas antes que o usuário seja atualizado para o TeamsOnly.

5. Atribua as Microsoft 365 ou Office 365, se necessário.  O usuário deve ter os Teams e Skype for Business Online 2 e Sistema de Telefonia. Se o Skype for Business Online 2 estiver desabilitado, habilite-o novamente.

6. Atualizar o usuário: essas etapas devem ser coordenadas.

   - Usando as ferramentas de Skype for Business local, execute Move-CsUser com a opção -MoveToTeams. Se você estiver usando uma versão do Skype for Business Server que não dá suporte à opção -MoveToTeams, primeiro execute o Move-CsUser e atribua o modo TeamsOnly no PowerShell remoto do locatário ou no console do Teams Administração.

   - No SBC, configure o roteamento de voz para habilitar chamadas de entrada enviando chamadas para Roteamento Direto em vez de para o Servidor de Mediação local.

   - Em Microsoft 365 ou Office 365: atribua o OnlineVoiceRoutingPolicy relevante para habilitar chamadas de saída.

## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>Do Skype for Business Server local, com o Enterprise Voice, ao Plano de Chamadas da Microsoft

Nesse cenário, o usuário ainda está hospedado Skype for Business local. A conectividade PSTN do usuário também é local. Para migrar esse usuário para o modo TeamsOnly com a funcionalidade PSTN, você deve mover o usuário para a nuvem e portar seu número da operadora antiga para um plano de Chamada da Microsoft ou atribuir um novo número ao usuário.

As etapas básicas estão listadas abaixo. As etapas 1 a 5 são listadas na sequência sugerida, mas podem ser feitas em qualquer ordem. Você deve concluir as Etapas 1 a 5 antes da Etapa 6.

1. Se você definir a política em todo o locatário para um dos modos Skype for Business, certifique-se de avôr usuários existentes das Ilhas atribuindo explicitamente o modo Ilhas, conforme descrito anteriormente.

2. Se você ainda não fez isso, [configure a organização para Skype for Business híbrido](/SkypeForBusiness/hybrid/configure-hybrid-connectivity).

3. Se desejar, configure várias Teams para esses usuários (por exemplo, TeamsMessagingPolicy, TeamsMeetingPolicy e assim por diante). Você pode configurar políticas a qualquer momento. No entanto, se você quiser garantir que os usuários tenham a configuração correta quando forem atualizados, configure essas políticas antes que o usuário seja atualizado para o TeamsOnly.

4. Atribua as Microsoft 365 ou Office 365, se necessário. O usuário deve ter os Teams e Skype for Business Online 2 e Sistema de Telefonia. Se o Skype for Business Online 2 estiver desabilitado, habilite-o novamente.

5. Obtenha números de telefone para seus usuários. (Para obter detalhes, [consulte Gerenciar números de telefone para sua organização](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).)

   - Se você estiver reutilizando os números, envie uma solicitação de portabilidade para sua operadora.
   - Como alternativa, você pode adquirir novos números diretamente da Microsoft.

6. Atualize o usuário e, se necessário, atribua o LineUri. Usando as ferramentas de Skype for Business local, execute Move-CsUser com a opção -MoveToTeams.

    - Se você estiver portando números para a Microsoft, deverá coordenar o tempo dessa operação para ocorrer quando a porta ocorrer.

    - Se você estiver usando novos números da Microsoft, precisará alterar o LineUri do usuário depois que o usuário for movido online usando Set-CsPhoneNumberAssignment.

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>Resumo da configuração por locatário do Roteamento Direto

1. Verifique se o Controlador de Borda de Sessão (SBC) tem suporte com o Roteamento Direto examinando [essa lista](direct-routing-border-controllers.md). Verifique também se você tem a versão correta do firmware.

2. Emparelhe seu SBC local com o serviço Teams Roteamento Direto. Para obter detalhes, [consulte Emparelhar o SBC com o serviço de Roteamento Direto Sistema de Telefonia](direct-routing-configure.md).

3. Essa configuração é essencialmente um espelho da configuração local. A configuração online consiste em:
   - OnlineVoiceRoutingPolicy (com base no VoiceRoutingPolicy local se estiver migrando usuários do Skype for Business Online e com base no VoicePolicy se migrar usuários do local com o Enterprise Voice).
   - Objetos OnlinePSTNUsage (com base no uso de PSTN local).
   - Objetos OnlineVoiceRoute (com base no VoiceRoute local).

Para obter mais informações, consulte [Configurar Roteamento Direto](direct-routing-configure.md).

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>Gerenciar a propriedade EnterpriseVoiceEnabled durante a migração

Seja usando o Roteamento Direto ou um plano de Chamada da Microsoft, um usuário deve ter EnterpriseVoiceEnabled=true no Azure AD para que o usuário tenha a funcionalidade PSTN.  EnterpriseVoiceEnabled ("habilitado para EV") é uma propriedade (não uma política) que existe em um diretório local e na nuvem. O valor na nuvem é o que importa para Teams.  A lógica exata de como a EV habilitada é definida como true depende do seguinte cenário:

- Se o usuário estiver habilitado para EV no Skype for Business Server local e uma licença do Sistema de Telefonia for atribuída ao usuário antes de mover o usuário para a nuvem com Move-CsUser, o usuário online será provisionado com EV-enabled=true.

- Se um usuário existente do TeamsOnly ou Skype for Business Online receber uma licença Sistema de Telefonia, habilitado para EV não será definido como true por padrão. Esse também é o caso se um usuário local for movido para a nuvem antes de atribuir a licença Sistema de Telefonia usuário. Em ambos os casos, o administrador deve especificar o seguinte cmdlet:

  ```PowerShell
  Set-CsPhoneNumberAssignment -EnterpriseVoiceEnabled $True
  ```

## <a name="related-links"></a>Links relacionados

[Planejar sua solução Teams voz](cloud-voice-landing-page.md)

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md)

[Configurar a conectividade híbrida entre Skype for Business Server e Microsoft 365 ou Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover os usuários entre um ambiente local e a nuvem](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[Usando o Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
