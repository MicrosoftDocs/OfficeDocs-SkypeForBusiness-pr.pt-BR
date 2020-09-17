---
title: Atualize para o Teams a partir de uma implantação local do Skype for Business-Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Atualização do Skype for Business para o Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 075960ef47f5d708a72cabc8e3c492786c2a5112
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940614"
---
# <a name="pstn-considerations-when-upgrading-to-teams-mdash-for-it-administrators"></a>Considerações de PSTN durante a atualização para o Microsoft Teams &mdash; para administradores de ti

Este artigo descreve as considerações da PSTN (rede telefônica pública comutada) durante a atualização para o Microsoft Teams. Este artigo é o sexto de vários que descrevem os conceitos de atualização e a implementação para administradores de ti.  

- [Visão geral](upgrade-to-teams-on-prem-overview.md)
- [Métodos de atualização](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Ferramentas para gerenciar a atualização](upgrade-to-teams-on-prem-tools.md)
- [Considerações adicionais sobre organizações com o Skype for Business no local](upgrade-to-teams-on-prem-considerations.md)
- [Implementar sua atualização](upgrade-to-teams-on-prem-implement.md)
- **Considerações sobre PSTN (rede telefônica pública comutada** ) (este artigo)

Além disso, os seguintes artigos descrevem conceitos importantes de atualização e comportamentos de coexistência:

- [Coexistência de Teams e Skype for Business](upgrade-to-teams-on-prem-coexistence.md)
- [Modos de coexistência-referência](migration-interop-guidance-for-teams-with-skype.md)
- [Experiência e conformidade do cliente do Teams a modos de coexistência](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > Só há suporte para o uso do sistema telefônico com Teams quando o usuário está no modo TeamsOnly.  Se o usuário estiver no modo de ilhas, o sistema telefônico só será compatível com o Skype for Business. 


## <a name="pstn-calling-scenarios"></a>Cenários de chamadas PSTN

Há quatro cenários de chamadas possíveis ao se mover para o modo TeamsOnly:

- [Um usuário no Skype for Business Online, com um plano de chamadas da Microsoft](#from-skype-for-business-online-with-microsoft-calling-plans). Após a atualização, este usuário continuará a ter um plano de chamadas da Microsoft.

- [Um usuário no Skype for Business Online, com funcionalidade de voz local](#from-skype-for-business-online-with-on-premises-voice) por meio do Skype for Business local ou da edição do Cloud Connector. A atualização do usuário para o Teams precisa ser coordenada com a migração do usuário para o roteamento direto para garantir que o usuário do TeamsOnly tenha funcionalidade PSTN.

- [Um usuário do Skype for Business no local com o Enterprise Voice](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), que será movido para online e mantendo a conectividade PSTN local.  Migrar este usuário para o Teams requer mover a conta do Skype for Business no local para a nuvem e coordenar essa movimentação com a migração do usuário para o roteamento direto. 

- [Um usuário do Skype for Business no local com o Enterprise Voice](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), que se moverá para online e usando um plano de chamadas da Microsoft.  Migrar este usuário para o Microsoft Teams requer mover a conta do Skype for Business no local para a nuvem e coordenar essa movimentação com uma a porta do número de telefone do usuário para um plano de chamadas da Microsoft ou B) atribuir um novo número de assinante de regiões disponíveis.

Este artigo fornece apenas uma visão geral de alto nível. Para obter mais informações, consulte planos de roteamento e [chamada](calling-plan-landing-page.md)do [sistema de telefonia direto](direct-routing-landing-page.md) . 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>Do Skype for Business online com planos de chamadas da Microsoft 

Este é o cenário de atualização mais simples que envolve voz. 

1. Certifique-se de que os usuários receberam uma licença do teams. Por padrão, quando você atribui uma licença do Microsoft 365 ou do Office 365, o Teams está habilitado, portanto, a menos que você tenha desabilitado anteriormente a licença do Teams, nenhuma ação deve ser necessária.

2.  Se os usuários já tiverem um plano de chamadas da Microsoft com um número de telefone, a única alteração necessária será atribuir o modo de TeamsOnly do usuário no TeamsUpgradePolicy.  Antes de atribuir o modo de TeamsOnly, as chamadas PSTN de entrada serão feitas no cliente Skype for Business do usuário. Após a atualização para o modo TeamsOnly, as chamadas PSTN de entrada serão enterradas no cliente do teams do usuário.  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>Do Skype for Business online com voz local

Nesse cenário, o usuário já está no Skype for Business Online, mas a conectividade PSTN é local, usando o Skype for Business Server no modo híbrido ou na edição do conector do Cloud. Migrar esses usuários para o modo TeamsOnly com funcionalidade PSTN significa habilitá-los para roteamento direto, no qual os troncos PSTN se conectam diretamente ao serviço de roteamento direto na nuvem, via SBC (controlador de borda de sessão local).

As etapas básicas estão listadas abaixo.  As etapas 1-4 são listadas na sequência sugerida, mas elas podem ser feitas em qualquer ordem. A chave é que todas elas devem ser concluídas antes da etapa 5.

1. Se você estiver definindo a política de todos os locatários como um dos modos do Skype for Business, não se esqueça de descrever todos os usuários de ilhas existentes, atribuindo explicitamente o modo de ilhas de ilhas, conforme descrito anteriormente.

2. Configure seu locatário para roteamento direto. Consulte o [Resumo da configuração por locatário do roteamento direto](#summary-of-per-tenant-configuration-of-direct-routing).

3. Se desejar, configure várias políticas de equipe para esses usuários (por exemplo, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.). Isso pode ser feito a qualquer momento, mas se você quiser garantir que os usuários tenham a configuração correta quando forem atualizados, é melhor fazer isso antes de o usuário ser atualizado para o modo TeamsOnly.

4. Preparar os usuários selecionados para a migração de voz: 
   - Se necessário, atribua a licença do teams.  Pressupondo que o usuário já esteja funcional na voz local do Skype for Business Online, o usuário já tem o plano 2 do Skype for Business e também o Microsoft Phone System. Deixe ambos os planos habilitados, incluindo a licença do Skype for Business online plano 2.  
   - Atribua o OnlineVoiceRoutingPolicy desejado. 

5. Atualize o usuário: essas etapas devem ser coordenadas. 

   - No Microsoft 365 ou no Office 365, atualize o usuário para o modo TeamsOnly (Grant-CsTeamsUpgradePolicy).
   - No SBC, configure o roteamento de voz para permitir chamadas recebidas enviando chamadas para roteamento direto em vez de para o servidor de mediação local.


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>No Skype for Business Server local, com o Enterprise Voice, para roteamento direto

Nesse cenário, o usuário ainda é hospedado no Skype for Business local, e a conectividade PSTN também é local. Migrar esses usuários para o modo TeamsOnly com funcionalidade PSTN significa habilitá-los para roteamento direto e, em seguida, mover o usuário para a nuvem. 
 
As etapas básicas estão listadas abaixo.  As etapas 1-5 são listadas na sequência sugerida, mas elas podem ser feitas em qualquer ordem. A chave é que todas elas devem ser concluídas antes da etapa 6.

1. Se você estiver definindo a política de todos os locatários como um dos modos do Skype for Business, não deixe de apresentar os usuários de ilhas existentes atribuindo explicitamente o modo de ilhas de ilhas, conforme descrito anteriormente.

2. Se você ainda não fez isso, [Configure a organização para o Skype for Business híbrido](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity).

3. Configure seu locatário para roteamento direto. Consulte o [Resumo da configuração por locatário do roteamento direto](#summary-of-per-tenant-configuration-of-direct-routing).

4. Se desejar, configure várias políticas de equipe para esses usuários (por exemplo, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.). Isso pode ser feito a qualquer momento, mas se você quiser garantir que os usuários tenham a configuração correta quando forem atualizados, é melhor fazer isso antes de o usuário ser atualizado para o TeamsOnly.

5. Atribua as licenças do Microsoft 365 ou do Office 365, se necessário.  O usuário deve ter o plano 2 do teams online e do Skype for Business Online, bem como o sistema telefônico. Se o Skype for Business online plano 2 estiver desabilitado, habilite-o novamente.  

6. Atualize o usuário: essas etapas devem ser coordenadas. 

   - Usando as ferramentas locais do Skype for Business, execute move-CsUser com a opção-MoveToTeams. Se você estiver usando uma versão do Skype for Business Server que não seja compatível com a opção MoveToTeams, primeiro execute move-CsUser e, em seguida, atribua o modo TeamsOnly no PowerShell remoto do locatário ou no console de administração do teams.

   - No SBC, configure o roteamento de voz para permitir chamadas recebidas enviando chamadas para roteamento direto em vez de para o servidor de mediação local. 

   - No Microsoft 365 ou no Office 365: atribua o OnlineVoiceRoutingPolicy relevante para habilitar as chamadas feitas. 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>No Skype for Business Server local, com o Enterprise Voice, para o plano de chamadas da Microsoft

Nesse cenário, o usuário ainda é hospedado no Skype for Business local, e a conectividade PSTN também é local. Migrar esses usuários para o modo TeamsOnly com funcionalidade PSTN significa mover o usuário para a nuvem e fazer a portabilidade do número da transportadora antiga para um plano de chamadas da Microsoft ou atribuir um novo número ao usuário. 

As etapas básicas estão listadas abaixo.As etapas 1-5 são listadas na sequência sugerida, mas elas podem ser feitas em qualquer ordem. A chave é que todas elas devem ser concluídas antes da etapa 6. 

1. Se você estiver definindo a política de todos os locatários como um dos modos do Skype for Business, não deixe de apresentar os usuários de ilhas existentes atribuindo explicitamente o modo de ilhas de ilhas, conforme descrito anteriormente. 

2. Se você ainda não fez isso, [Configure a organização para o Skype for Business híbrido](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity). 

3. Se desejar, configure várias políticas de equipe para esses usuários (por exemplo, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.). Isso pode ser feito a qualquer momento, mas se você quiser garantir que os usuários tenham a configuração correta quando forem atualizados, é melhor fazer isso antes de o usuário ser atualizado para o TeamsOnly. 

4. Atribua as licenças do Microsoft 365 ou do Office 365, se necessário.O usuário deve ter o plano 2 do teams online e do Skype for Business Online, bem como o sistema telefônico. Se o Skype for Business online plano 2 estiver desabilitado, habilite-o novamente.  

5. Obter números de telefone para seus usuários. (Para obter detalhes, consulte [gerenciar números de telefone para sua organização](https://docs.microsoft.com/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).)

   - Se você for reutilizar os números, envie uma solicitação de portabilidade para a sua operadora.  
   - Você também pode adquirir novos números diretamente da Microsoft. 

6. Atualize o usuário e, se necessário, atribua LineUri. Usando as ferramentas locais do Skype for Business, execute move-CsUser com a opção-MoveToTeams.  

    - Se estiver transportando números para a Microsoft, você deve coordenar o intervalo dessa operação para ocorrer quando a porta ocorrer. 

    - Se você estiver usando novos números da Microsoft, será necessário alterar o LineUri para o usuário. Isso deve ser feito após o usuário ser movido online usando Set-CsOnlineVoiceUser.  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>Resumo da configuração por locatário do roteamento direto 

1. Verifique se o seu controlador de borda de sessão (SBC) é compatível com o roteamento direto analisando [esta lista](direct-routing-border-controllers.md). Você também deve certificar-se de que tem a versão correta do firmware.  

2. Emparelhar seu SBC local com o serviço de roteamento Direct Teams. Para obter detalhes, consulte [emparelhar o SBC com o serviço de roteamento direto do sistema telefônico](direct-routing-configure.md). 

3. Essa configuração é essencialmente um espelho da configuração local. A configuração online consiste em: 
   - OnlineVoiceRoutingPolicy (com base no VoiceRoutingPolicy local, com a migração de usuários do Skype for Business Online e com base em VoicePolicy se migrar usuários do local com o Enterprise Voice).
   - Objetos OnlinePSTNUsage (com base no uso de PSTN local). 
   - Objetos OnlineVoiceRoute (baseados em VoiceRoutes locais). 

Para obter mais informações, consulte [Configurar o roteamento direto](direct-routing-configure.md). 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>Gerenciar a propriedade EnterpriseVoiceEnabled durante a migração 

Seja usando o roteamento direto ou um plano de chamadas da Microsoft, um usuário deve ter EnterpriseVoiceEnabled = true no Azure AD para que o usuário tenha a funcionalidade PSTN.  EnterpriseVoiceEnabled ("EV-Enabled") é uma propriedade (não uma política) que existe em um diretório local e na nuvem. O valor na nuvem é o que importa para o Teams.  A lógica exata para a maneira como o habilitado para EV é definida como true depende do seguinte cenário: 

- Se o usuário for compatível com EV no local Skype for Business Server e uma licença do sistema de telefonia for atribuída ao usuário antes de passar o usuário para a nuvem com move-CsUser, o usuário online será provisionado com EV-Enabled = true. 

- Se um usuário existente do TeamsOnly ou do Skype for Business Online for atribuído a uma licença do sistema de telefonia, o EV-Enabled não será definido como true por padrão.  Esse também será o caso se um usuário local for movido para a nuvem antes de atribuir a licença do sistema telefônico. Em ambos os casos, o administrador deve especificar o seguinte cmdlet: 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a>Links relacionados

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover os usuários entre um ambiente local e a nuvem](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usando o Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

