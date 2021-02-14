---
title: Considerações do PSTN ao atualizar para o Teams a partir de uma implantação local do Skype for Business
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Considerações de voz para a atualização do Skype for Business para o Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a9783f5d60e5a595d548bbfc83ee013500934ed
ms.sourcegitcommit: b816ae9de91f3d01e795a69a00465a70003069b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49686427"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a>Considerações do PSTN para a atualização para o Teams do Skype for Business local

Este artigo descreve considerações sobre A Rede Telefônica Pública Comutado (PSTN) ao atualizar para o Teams.   


Além disso, os artigos a seguir descrevem conceitos de atualização importantes e comportamentos de coexistência:

- [Coexistência do Teams e do Skype for Business](upgrade-to-teams-on-prem-coexistence.md)
- [Modos de coexistência - Referência](migration-interop-guidance-for-teams-with-skype.md)
- [Experiência e conformidade do cliente do Teams a modos de coexistência](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > - O uso do Sistema telefônico com o Teams só é suportado quando o usuário está no modo TeamsOnly.  Se o usuário estiver no modo Ilhas, o Sistema telefônico só tem suporte com o Skype for Business. 
 > - As configurações de encaminhamento de chamadas, grupo de chamada de equipe e delegação do Skype for Business não são migradas e precisarão ser recriadas para o Teams.
 > - Para ter uma visão geral dos recursos de voz na nuvem do Microsoft Teams e ajudar a decidir qual solução de voz da Microsoft é ideal para sua organização, consulte Planejar sua solução de voz [do Teams.](cloud-voice-landing-page.md)


## <a name="pstn-calling-scenarios"></a>Cenários de chamada PSTN

Há quatro cenários de chamada possíveis ao mover para o modo TeamsOnly:

- [Um usuário no Skype for Business Online, com um Plano de Chamada da Microsoft.](#from-skype-for-business-online-with-microsoft-calling-plans) Após a atualização, esse usuário continuará a ter um plano de Chamada da Microsoft.

- [Um usuário no Skype for Business Online,](#from-skype-for-business-online-with-on-premises-voice) com funcionalidade de voz local por meio do Skype for Business local ou do Cloud Connector Edition. A atualização do usuário para o Teams precisa ser coordenada com a migração do usuário para o Roteamento Direto para garantir que o usuário do TeamsOnly tenha funcionalidade PSTN.

- [Um usuário no Skype for Business local](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)com o Enterprise Voice, que se move para a internet e mantém a conectividade PSTN local.  Migrar esse usuário para o Teams requer mover a conta do Skype for Business local do usuário para a nuvem e coordenar essa movimentação com a migração do usuário para o Roteamento Direto. 

- [Um usuário no Skype for Business local com](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)o Enterprise Voice, que vai se mudar para a Internet e usar um plano de Chamada da Microsoft.  Migrar esse usuário para o Teams requer mover a conta do Skype for Business local do usuário para a nuvem e coordenar essa movimentação com A) a porta do número de telefone desse usuário para um Plano de Chamada da Microsoft ou B) atribuindo um novo número de assinante de regiões disponíveis.

Este artigo fornece apenas uma visão geral de alto nível. Para obter mais informações, consulte [Planos de Roteamento](direct-routing-landing-page.md) Direto e Chamadas do Sistema [de Telefonia.](calling-plan-landing-page.md) 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>Do Skype for Business Online com planos de Chamada da Microsoft 

Este é o cenário de atualização mais simples envolvendo voz. 

1. Certifique-se de que os usuários tenham sido atribuídos uma licença do Teams. Por padrão, quando você atribui uma licença do Microsoft 365 ou do Office 365, o Teams está habilitado, portanto, a menos que você tenha desabilitado anteriormente a licença do Teams, nenhuma ação deve ser necessária.

2.  Se os usuários já têm um Plano de Chamada da Microsoft com um número de telefone, a única alteração necessária é atribuir o modo TeamsOnly do usuário no TeamsUpgradePolicy.  Antes de atribuir o modo TeamsOnly, as chamadas PSTN de entrada chegarão no cliente Skype for Business do usuário. Após a atualização para o modo TeamsOnly, as chamadas PSTN de entrada chegarão no cliente do Teams do usuário.  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>Do Skype for Business Online com voz local

Nesse cenário, o usuário já está no Skype for Business Online, mas sua conectividade PSTN está no local, usando o Skype for Business Server no modo híbrido ou o Cloud Connector Edition. Migrar esses usuários para o modo TeamsOnly com a funcionalidade PSTN significa habilita-los para Roteamento Direto, no qual troncos PSTN se conectam diretamente ao serviço roteamento direto na nuvem, por meio do SBC (Controlador de Borda de Sessão) local.

As etapas básicas estão listadas abaixo.  As etapas 1 a 4 são listadas na sequência sugerida, mas podem ser feitas em qualquer ordem. A chave é que todos eles devem ser concluídos antes da Etapa 5.

1. Se você estiver definindo a política em todo o locatário para um dos modos do Skype for Business, certifique-se de desacatar todos os usuários de Ilhas existentes atribuindo explicitamente o modo Ilhas, conforme descrito anteriormente.

2. Configure seu locatário para Roteamento Direto. Consulte [Resumo da configuração por locatário do Roteamento Direto.](#summary-of-per-tenant-configuration-of-direct-routing)

3. Se desejar, configure várias políticas do Teams para esses usuários (por exemplo, TeamsMessagingPolicy, TeamsMeetingPolicy etc.). Isso pode ser feito a qualquer momento, mas se você quiser garantir que os usuários tenham a configuração correta quando eles são atualizados, é melhor fazer isso antes que o usuário seja atualizado para o modo TeamsOnly.

4. Preparar usuários selecionados para a migração de voz: 
   - Se necessário, atribua a licença do Teams.  Supondo que o usuário já está funcional na voz local do Skype for Business Online, o usuário já tem o Plano 2 do Skype for Business e o Microsoft Phone System. Deixe os dois planos habilitados, incluindo a licença do Skype for Business Online Plano 2.  
   - Atribua o OnlineVoiceRoutingPolicy desejado. 

5. Atualizar o usuário: estas etapas devem ser coordenadas. 

   - No Microsoft 365 ou no Office 365, atualize o usuário para o modo TeamsOnly (Grant-CsTeamsUpgradePolicy).
   - No SBC, configure o roteamento de voz para habilitar chamadas de entrada enviando chamadas para Roteamento Direto, em vez de para o Servidor de Mediação local.


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>Do Skype for Business Server local, com o Enterprise Voice, ao Roteamento Direto

Nesse cenário, o usuário ainda está instalado no Skype for Business local, e sua conectividade PSTN também é local. Migrar esses usuários para o modo TeamsOnly com a funcionalidade PSTN significa habilita-los para Roteamento Direto e, em seguida, mover o usuário para a nuvem. 
 
As etapas básicas estão listadas abaixo.  As etapas de 1 a 5 são listadas na sequência sugerida, mas podem ser feitas em qualquer ordem. A chave é que todos eles devem ser concluídos antes da Etapa 6.

1. Se você estiver definindo a política em todo o locatário para um dos modos do Skype for Business, certifique-se de falar com os usuários de Ilhas existentes atribuindo explicitamente o modo Ilhas, conforme descrito anteriormente.

2. Se você ainda não fez isso, configure a organização para [o Skype for Business híbrido.](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

3. Configure seu locatário para Roteamento Direto. Consulte [Resumo da configuração por locatário do Roteamento Direto.](#summary-of-per-tenant-configuration-of-direct-routing)

4. Se desejar, configure várias políticas do Teams para esses usuários (por exemplo, TeamsMessagingPolicy, TeamsMeetingPolicy etc.). Isso pode ser feito a qualquer momento, mas se você quiser garantir que os usuários tenham a configuração correta quando eles são atualizados, é melhor fazer isso antes que o usuário seja atualizado para o TeamsOnly.

5. Atribua as licenças do Microsoft 365 ou do Office 365, se necessário.  O usuário deve ter o Teams e o Skype for Business Online Plano 2, bem como o Sistema telefônico. Se o Plano 2 do Skype for Business Online estiver desabilitado, rehabilita-o.  

6. Atualizar o usuário: estas etapas devem ser coordenadas. 

   - Usando as ferramentas locais do Skype for Business, execute Move-CsUser com a opção -MoveToTeams. Se você estiver usando uma versão do Skype for Business Server que não dê suporte à opção -MoveToTeams, primeiro execute o Move-CsUser e, em seguida, atribua o modo TeamsOnly no PowerShell remoto do locatário ou no Console de Administração do Teams.

   - No SBC, configure o roteamento de voz para habilitar chamadas de entrada enviando chamadas para Roteamento Direto, em vez de para o Servidor de Mediação local. 

   - No Microsoft 365 ou no Office 365: atribua o OnlineVoiceRoutingPolicy relevante para habilitar chamadas de saída. 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>Do Skype for Business Server local, com o Enterprise Voice, ao Plano de Chamada da Microsoft

Nesse cenário, o usuário ainda está instalado no Skype for Business local, e sua conectividade PSTN também é local. Migrar esses usuários para o modo TeamsOnly com a funcionalidade PSTN significa mover o usuário para a nuvem e portar o número da operadora antiga para um plano de Chamada da Microsoft ou atribuir um novo número ao usuário. 

As etapas básicas estão listadas abaixo.As etapas de 1 a 5 são listadas na sequência sugerida, mas podem ser feitas em qualquer ordem. A chave é que todos eles devem ser concluídos antes da Etapa 6. 

1. Se você estiver definindo a política em todo o locatário para um dos modos do Skype for Business, certifique-se de falar com os usuários de Ilhas existentes atribuindo explicitamente o modo Ilhas, conforme descrito anteriormente. 

2. Se você ainda não fez isso, configure a organização para [o Skype for Business híbrido.](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) 

3. Se desejar, configure várias políticas do Teams para esses usuários (por exemplo, TeamsMessagingPolicy, TeamsMeetingPolicy etc.). Isso pode ser feito a qualquer momento, mas se você quiser garantir que os usuários tenham a configuração correta quando eles são atualizados, é melhor fazer isso antes que o usuário seja atualizado para o TeamsOnly. 

4. Atribua as licenças do Microsoft 365 ou do Office 365, se necessário.O usuário deve ter o Teams e o Skype for Business Online Plano 2, bem como o Sistema telefônico. Se o Plano 2 do Skype for Business Online estiver desabilitado, rehabilita-o.  

5. Obter números de telefone para seus usuários. (Para obter detalhes, [consulte Gerenciar números de telefone para sua organização.)](https://docs.microsoft.com/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

   - Se você estiver usando os números de novo, envie uma solicitação de portação para sua operadora.  
   - Como alternativa, você pode adquirir novos números diretamente da Microsoft. 

6. Atualize o usuário e, se necessário, atribua o LineUri. Usando as ferramentas locais do Skype for Business, execute Move-CsUser com a opção -MoveToTeams.  

    - Se você estiver portando números para a Microsoft, deverá coordenar o tempo dessa operação para ocorrer quando a porta ocorrer. 

    - Se você estiver usando novos números da Microsoft, precisará alterar o LineUri do usuário. Isso deve ser feito depois que o usuário for movido online usando Set-CsOnlineVoiceUser.  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>Resumo da configuração por locatário do Roteamento Direto 

1. Verifique se seu Controlador de Borda de Sessão (SBC) tem suporte com Roteamento Direto ao revisar [esta lista.](direct-routing-border-controllers.md) Você também deve garantir que tenha a versão correta do firmware.  

2. Emparelhe seu SBC local com o serviço de Roteamento Direto do Teams. Para obter detalhes, [consulte Emparelhar o SBC ao serviço de Roteamento Direto do Sistema telefônico.](direct-routing-configure.md) 

3. Essa configuração é essencialmente um espelho da configuração local. A configuração online consiste em: 
   - OnlineVoiceRoutingPolicy (com base no VoiceRoutingPolicy local se migrar usuários do Skype for Business Online e com base no VoicePolicy se migrar usuários locais com o Enterprise Voice).
   - Objetos OnlinePSTNUsage (com base no uso de PSTN local). 
   - Objetos do OnlineVoiceRoute (com base no VoiceRoute local). 

Para obter mais informações, consulte [Configurar Roteamento Direto.](direct-routing-configure.md) 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>Gerenciar a propriedade EnterpriseVoiceEnabled durante a migração 

Seja usando o Roteamento Direto ou um plano de Chamada da Microsoft, um usuário deve ter EnterpriseVoiceEnabled=true no Azure AD para que o usuário tenha funcionalidade PSTN.  EnterpriseVoiceEnabled ("habilitado para EV") é uma propriedade (não uma política) que existe em um diretório local e na nuvem. O valor na nuvem é o que importa para o Teams.  A lógica exata de como o recurso habilitado para EV é definido como verdadeiro depende do seguinte cenário: 

- Se o usuário estiver habilitado para EV no Skype for Business Server local e uma licença do Sistema de Telefonia for atribuída ao usuário antes de mover o usuário para a nuvem com o Move-CsUser, o usuário online será provisionado com EV-enabled=true. 

- Se um usuário existente do TeamsOnly ou do Skype for Business Online tiver uma licença do Sistema de Telefonia, habilitado para EV não será definido como verdadeiro por padrão.  Esse também é o caso se um usuário local for movido para a nuvem antes de atribuir a licença do Sistema de Telefonia. Em ambos os casos, o administrador deve especificar o seguinte cmdlet: 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a>Links relacionados

[Planejar sua solução de voz do Teams](cloud-voice-landing-page.md)

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover os usuários entre um ambiente local e a nuvem](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usando o Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

