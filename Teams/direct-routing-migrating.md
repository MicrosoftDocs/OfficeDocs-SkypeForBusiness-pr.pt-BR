---
title: Migrando para o roteamento direto
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Saiba o que é necessário para migrar o roteamento direto de um Skype para Business Online e perspectiva de configuração de equipes.
ms.openlocfilehash: 4a1cb3d96d6f5d024b8da6a42288b09b3a8cde3d
ms.sourcegitcommit: 2f3d105203edbc21bbbb9c17390b1d3011ef4546
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2018
ms.locfileid: "20084403"
---
# <a name="migrating-to-direct-routing"></a>Migrando para o roteamento direto

Este artigo descreve o que é necessário para migrar o roteamento direto de um Skype para Business Online e Teams Microsoft perspectiva de configuração. Este artigo aborda migrando dentre os seguintes: 
 
- Sistema de telefone do Office 365 com as chamadas de planos (para equipes e Skype para negócios Online) 
- Sistema de telefone do Office 365 com conectividade PSTN local no Skype para Business Server (para Skype para negócios Online)  
- Sistema de telefone do Office 365 com conectividade PSTN de local, usando a edição do conector de nuvem (Skype para Business Online)

  
Além das etapas de configuração, configuração também é necessária no controlador de borda de sessão (SBC) para rotear as chamadas para a nova rota. Que está fora do escopo deste documento. Para obter mais informações, consulte a documentação do fornecedor SBC.  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a>Estado final para várias opções de conectividade PSTN de provisionamento de usuário 

A tabela a seguir mostra o estado final de um usuário provisionado para as opções selecionadas da conectividade PSTN com sistema de telefone do Office 365. Apenas os atributos relevantes para voz são mostrados.

|Atributos de objeto do usuário |Sistema de Telefonia com Planos de Chamadas|Telefone sistema com o local a conectividade PSTN via Skype para Business Server|Telefone de sistema com o local a conectividade de PSTN por meio do conector de nuvem|Telefone sistema com o local a conectividade PSTN por meio de roteamento direto|
|---|---|---|---|---|
|Cliente|Skype para equipes ou comercial |Skype for Business |Skype for Business |Microsoft Teams|
|Licenças|Negócios on-line do Skype</br>Plano 2</br></br>MCOProfessional ou MCOSTANDARD)</br></br></br>Sistema telefônico (MCOEV)</br></br></br>Planos de Chamadas</br>Microsoft Teams|Skype Business Online plano 2 (MCOProfessional ou MCOSTANDARD)</br></br></br>Sistema telefônico (MCOEV)|Skype Business Online plano 2 (MCOProfessional ou MCOSTANDARD)</br></br></br>Sistema telefônico (MCOEV)|Skype Business Online plano 2 (MCOProfessional ou MCOSTANDARD</br></br></br>Sistema telefônico (MCOEV)</br></br>Microsoft Teams|
OnPremLineURI |N/D|O número de telefone deve ser sincronizado a partir do local AD. |O número de telefone pode ser gerenciado no Active Directory no local ou no Windows Azure Active Directory.|O número de telefone pode ser gerenciado no Active Directory no local ou no Windows Azure Active Directory. No entanto, se a organização tiver Skype local para a empresa, o número deve ser sincronizado do Active Directory local.|
|LineURI|Número de telefone de chamada de PSTN|Definir automaticamente do parâmetro OnPremLineURI|Definir automaticamente do parâmetro OnPremLineURI|Definir automaticamente do parâmetro OnPremLineURI|
|EnterpriseVoiceEnabled|True|True|True|True|
|HostedVoiceMail |True|True|True|True|
|VoicePolicy|BusinessVoice|HybridVoice|HybridVoice|HybridVoice|
|Hostedvoicemailpolicy, que |BusinessVoice|BusinessVoice|BusinessVoice|BusinessVoice|
|VoiceRoutingPolicy|Tem um valor|Tem um valor|Tem um valor|N/D|
|OnlineVoiceRoutingPolicy|$Null|$Null|$Null|Tem um valor|
|TeamsUpgradePolicy<sup>1</sup>|TeamsOnly, SfBOnly ou Ilhas|$Null|$Null|Ilhas ou TeamsOnly|
|TeamsInterPolicy<sup>2</sup></br>CallingDefaultClient –, leia a observação abaixo.|Equipes ou SfB |SfB|SfB|Microsoft Teams|
|TeamsCallingPolicy</br>AllowPrivateCalling|Verdadeiro|N/D|N/D|Verdadeiro|
|TeamsCallingPolicy</br>AllowGroupCalling|Verdadeiro|N/D|N/D|Verdadeiro|
||||||

<sup>1</sup> Escolher o modo certo do TeamsUpgradePolicy depende do cenário. Leia sobre a experiência de voz em diferentes modos de [migração e interoperabilidade orientações para as organizações](migration-interop-guidance-for-teams-with-skype.md)usando equipes em conjunto com o Skype para negócios.

<sup>2</sup> Como anunciada anteriormente, TeamsInteropPolicy será desativado (direcionado para o final do T3) e sua funcionalidade está sendo consolidada em TeamsUpgradePolicy. Interoperabilidade e migração serão gerenciados usando "modo de coexistência", conforme determinado pela TeamsUpgradePolicy, que agora está disponível. Seleção de modo do usuário orientará ambos os roteamento de chamadas de entrada e de bate-papos e no qual cliente o usuário pode iniciar o bate-papos e chamadas ou agendar reuniões. Enquanto TeamsInteropPolicy será desativado, ele ainda precisa ser definida em paralelo com TeamsUpgradePolicy durante a phaseout.  

Como parte desse esforço, a Microsoft recentemente atualizou o "Microsoft equipes & Skype para Business Admin Center" (também conhecido como Portal moderno) para refletir o novo modelo de gerenciamento com base em modos de coexistência. No Portal moderno, configurar TeamsUpgradePolicy serão automaticamente agora também definir TeamsInteropPolicy como valor consistente, portanto TeamsInteropPolicy não mais é exposta na interface do usuário. No entanto, os administradores usando o PowerShell ainda devem definir TeamsUpgradePolicy tanto TeamsInteropPolicy juntos para garantir o roteamento apropriado. Após concluir a transição para TeamsUpgradePolicy, não será necessário para definir também TeamsInteropPolicy.

Para obter mais informações, consulte [migração e interoperabilidade orientações para as organizações que usam equipes em conjunto com o Skype para negócios](migration-interop-guidance-for-teams-with-skype.md).

## <a name="migrating-from-calling-plans"></a>Migrando liguem para planos

Para obter mais informações sobre a migração do chamar planos, consulte:

- [Configurar Planos de Chamadas](https://docs.microsoft.com/en-us/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [Set-CsOnlineVoice usuário](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [Get-CsOnlineLisLocation](https://docs.microsoft.com/en-us/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
É recomendável que você remova previouslycconfigured as informações de plano de licenciamento da seguinte maneira:
 
```
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Migrando do sistema do Office 365 telefônico com conectividade PSTN local no Skype para Business Server

Para obter mais informações sobre a migração do sistema telefônico com conectividade PSTN local no Skype para Business Server, consulte o seguinte:

- [Planejamento](https://technet.microsoft.com/en-us/library/mt455212.aspx)
- [Implantando](https://technet.microsoft.com/en-us/library/mt634319.aspx) 

É recomendável que você remova as seguintes informações de roteamento de voz previamente configurado:

```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a>Migrando do sistema do Office 365 telefônico com conectividade PSTN de local por meio da edição do conector de nuvem 

Para obter mais informações sobre a migração do sistema telefônico com conectividade PSTN de local por meio do conector de nuvem, consulte o seguinte:

- [Planejamento](https://technet.microsoft.com/en-us/library/mt605227.aspx)  
- [Implantando](https://technet.microsoft.com/en-us/library/mt634319.aspx)
- [Configuração do usuário](https://docs.microsoft.com/en-us/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

É recomendável que você remova as seguintes informações de roteamento de voz previamente configurado:
 
```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a>LINKS RELACIONADOS

[Diretrizes de migração e interoperabilidade para organizações que usam equipes em conjunto com o Skype para negócios](migration-interop-guidance-for-teams-with-skype.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[New-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTeamsUpgradePolicy)

[Remove-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[Set-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)

