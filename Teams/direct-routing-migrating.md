---
title: Migrar para o roteamento direto
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Saiba o que é necessário para migrar para o roteamento direto de uma perspectiva de configuração do Skype for Business Online e do teams.
ms.openlocfilehash: c9c8cafdf6e49dc127dee4cb76a92dae13b5c0b9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290419"
---
# <a name="migrate-to-direct-routing"></a>Migrar para o roteamento direto

Este artigo descreve o que é necessário para migrar para o roteamento direto de uma perspectiva de configuração do Skype for Business Online e do Microsoft Teams. Este artigo aborda a migração da seguinte maneira: 
 
- Sistema telefônico do Office 365 com planos de chamadas (para Teams e Skype for Business online) 
- Sistema telefônico do Office 365 com conectividade PSTN local no Skype for Business Server (para Skype for Business online)  
- Sistema telefônico do Office 365 com conectividade PSTN local usando o Cloud Connector Edition (para Skype for Business online)

  
Além dessas etapas de configuração, a configuração também é necessária no SBC (controlador de borda de sessão) para direcionar as chamadas para a nova rota. Que está fora do escopo deste documento. Para obter mais informações, consulte a documentação do seu fornecedor de SBC.  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a>Estado final do provisionamento de usuário para várias opções de conectividade PSTN 

A tabela a seguir mostra o estado final de um usuário provisionado para as opções de conectividade PSTN selecionadas com o sistema telefônico do Office 365. Somente os atributos relevantes para voz são exibidos.

|Atributos de objeto de usuário |Sistema telefônico com planos de chamada|Sistema telefônico com conectividade PSTN local via Skype for Business Server|Sistema telefônico com conectividade PSTN local via conector de nuvem|Sistema telefônico com conectividade PSTN local via roteamento direto|
|---|---|---|---|---|
|Cliente|Skype for Business ou Teams |Skype for Business |Skype for Business |Microsoft Teams|
|Las|Skype Business Online</br>Plano 2</br></br>MCOProfessional ou MCOSTANDARD)</br></br></br>Sistema telefônico (MCOEV)</br></br></br>Planos de Chamadas</br>Microsoft Teams|Skype Business online plano 2 (MCOProfessional ou MCOSTANDARD)</br></br></br>Sistema telefônico (MCOEV)|Skype Business online plano 2 (MCOProfessional ou MCOSTANDARD)</br></br></br>Sistema telefônico (MCOEV)|Skype Business online plano 2 (MCOProfessional ou MCOSTANDARD</br></br></br>Sistema telefônico (MCOEV)</br></br>Microsoft Teams|
OnPremLineURI |N/D|O número de telefone deve ser sincronizado do anúncio local. |O número de telefone pode ser gerenciado tanto no Active Directory local quanto no Azure Active Directory.|O número de telefone pode ser gerenciado tanto no Active Directory local quanto no Azure Active Directory. No entanto, se a organização tiver o Skype for Business local, o número deverá ser sincronizado do Active Directory local.|
|LineURI|Número de telefone para chamadas PSTN|Definir automaticamente a partir do parâmetro OnPremLineURI|Definir automaticamente a partir do parâmetro OnPremLineURI|Definir automaticamente a partir do parâmetro OnPremLineURI|
|EnterpriseVoiceEnabled|True|True|True|True|
|HostedVoiceMail |True|True|True|True|
|VoicePolicy|BusinessVoice|HybridVoice|HybridVoice|HybridVoice|
|HostedVoiceMailPolicy |BusinessVoice|BusinessVoice|BusinessVoice|BusinessVoice|
|VoiceRoutingPolicy|Tem um valor|Tem um valor|Tem um valor|N/D|
|OnlineVoiceRoutingPolicy|$Null|$Null|$Null|Tem um valor|
|TeamsUpgradePolicy<sup>1</sup>|TeamsOnly, SfBOnly ou ilhas|$Null|$Null|Ilhas ou TeamsOnly|
|TeamsInterPolicy<sup>2</sup></br>CallingDefaultClient – Leia a observação abaixo.|Teams ou SfB |SfB|SfB|Microsoft Teams|
|TeamsCallingPolicy</br>AllowPrivateCalling|True|N/D|N/D|True|
|TeamsCallingPolicy</br>AllowGroupCalling|True|N/D|N/D|True|
||||||

<sup>1</sup> Escolher o modo correto do TeamsUpgradePolicy depende do cenário. Leia sobre a experiência de voz em diferentes modos na [Guia de migração e interoperabilidade para organizações que usam o Skype for Business](migration-interop-guidance-for-teams-with-skype.md).

<sup>2</sup> Como anunciado anteriormente, o TeamsInteropPolicy será desativado (direcionado para o fim do 3º trimestre) e sua funcionalidade será consolidada no TeamsUpgradePolicy. A interoperabilidade e a migração serão gerenciadas usando o "modo de coexistência" conforme determinado pela TeamsUpgradePolicy, que agora está disponível. A seleção do modo do usuário regerá o roteamento de chamadas de entrada e chats e em qual cliente o usuário pode iniciar chats e chamadas ou agendar reuniões. Embora o TeamsInteropPolicy seja desativado, ele ainda precisa ser definido em paralelo com o TeamsUpgradePolicy durante a fase de fase de tempo.  

Como parte desse esforço, a Microsoft atualizou recentemente o "centro de administração do Microsoft Teams" (também conhecido como portal moderno) para refletir o novo modelo de gerenciamento com base nos modos de coexistência. No portal moderno, configurar o TeamsUpgradePolicy agora também definirá TeamsInteropPolicy como valor consistente, portanto, o TeamsInteropPolicy não será mais exposto na interface do usuário. No entanto, os administradores que usam o PowerShell ainda devem definir TeamsUpgradePolicy e TeamsInteropPolicy juntos para garantir o roteamento adequado. Após a conclusão da transição para TeamsUpgradePolicy, ela não será mais necessária também para definir o TeamsInteropPolicy.

Para obter mais informações, consulte o [Guia de migração e interoperabilidade para organizações que usam o Microsoft Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md).

## <a name="migrating-from-calling-plans"></a>Migrando de planos de chamada

Para obter mais informações sobre como migrar de planos de chamada, consulte:

- [Configurar Planos de Chamadas](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [Usuário Set-CsOnlineVoice](https://docs.microsoft.com/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [Get-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
É recomendável que você remova as informações do plano de licenciamento do previouslycconfigured da seguinte maneira:
 
```
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Migrando do sistema telefônico do Office 365 com conectividade PSTN local no Skype for Business Server

Para obter mais informações sobre como migrar do sistema telefônico com conectividade PSTN local no Skype for Business Server, consulte o seguinte:

- [Planejamento](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [Implantação](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

É recomendável remover as informações de roteamento de voz configuradas anteriormente da seguinte maneira:

```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a>Migrando do sistema telefônico do Office 365 com conectividade PSTN local via Cloud Connector Edition 

Para obter mais informações sobre como migrar do sistema telefônico com conectividade PSTN local via conector de nuvem, consulte o seguinte:

- [Planejamento](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [Implantação](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [Configuração do usuário](https://docs.microsoft.com/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

É recomendável remover as informações de roteamento de voz configuradas anteriormente da seguinte maneira:
 
```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a>LINKS RELACIONADOS

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md)

[Grant CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[New-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsUpgradePolicy)

[Remove-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[Set-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)

