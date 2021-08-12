---
title: Migrar para o Roteamento Direto
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
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Saiba o que é necessário para migrar para o Roteamento Direto de uma perspectiva de configuração do Skype for Business Online e do Teams.
ms.openlocfilehash: bcc31554428c847fc9eb3c45804be42e850b30f943fadcc3ef6e245d07c9d4fb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54301996"
---
# <a name="migrate-to-direct-routing"></a>Migrar para o Roteamento Direto

Este artigo descreve o que é necessário para migrar para o Roteamento Direto de uma perspectiva de configuração do Skype for Business Online e do Teams. Este artigo aborda a migração dos seguintes sistemas: 
 
- Sistema de Telefonia com Planos de Chamada (para Teams e Skype for Business Online) 
- Sistema de Telefonia com conectividade PSTN local no Skype for Business Server (para Skype for Business Online)  
- Sistema de Telefonia com conectividade PSTN local usando o Cloud Connector Edition (para Skype for Business Online)


Além dessas etapas de configuração, também é necessário configurar o Controlador de Borda de Sessão (SBC) para direcionar as chamadas para a nova rota. Isso está fora do escopo deste documento. Para obter mais informações, consulte a documentação do seu fornecedor de SBC.  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a>Provisionamento de usuário estado final para várias opções de conectividade PSTN 

A tabela a seguir mostra o estado final de um usuário provisionado para as opções de conectividade PSTN selecionadas com Sistema de Telefonia. São exibidos somente os atributos relevantes para voz.

|Atributos de objeto do usuário |Sistema de Telefonia com Planos de Chamadas|Sistema de Telefonia com conectividade PSTN local por meio do Skype for Business Server|Sistema de Telefonia com conectividade PSTN via Cloud Connector|Sistema de Telefonia com conectividade PSTN local por meio de Roteamento Direto|
|---|---|---|---|---|
|Cliente|Skype for Business ou Teams |Skype for Business |Skype for Business |Teams|
|Licenças|Skype Business Online</br>Plano 2</br></br>MCOProfessional ou MCOSTANDARD)</br></br></br>Sistema de Telefonia (MCOEV)</br></br></br>Planos de Chamadas</br>Teams|Skype Business Online plano 2 (MCOProfessional ou MCOSTANDARD)</br></br></br>Sistema de Telefonia (MCOEV)|Skype Business Online plano 2 (MCOProfessional ou MCOSTANDARD)</br></br></br>Sistema de Telefonia (MCOEV)|Skype Business Online plano 2 (MCOProfessional ou MCOSTANDARD</br></br></br>Sistema de Telefonia (MCOEV)</br></br>Teams|
OnPremLineURI |Não disponível|O número de telefone deve ser sincronizado a partir do AD local. |O número de telefone pode ser gerenciado em um Active Directory local ou no Azure Active Directory.|O número de telefone pode ser gerenciado em um Active Directory local ou no Azure Active Directory. No entanto, se a organização tiver o Skype for Business local, o número deve ser sincronizado com o Active Directory local.|
|LineURI|Número de telefone de chamada PSTN|Definir automaticamente a partir do parâmetro OnPremLineURI|Definir automaticamente a partir do parâmetro OnPremLineURI|Definir automaticamente a partir do parâmetro OnPremLineURI|
|EnterpriseVoiceEnabled|Verdadeiro|Verdadeiro|Verdadeiro|Verdadeiro|
|HostedVoiceMail |Verdadeiro|Verdadeiro|Verdadeiro|Verdadeiro|
|VoicePolicy|BusinessVoice |HybridVoice|HybridVoice|HybridVoice|
|HostedVoicemailPolicy |BusinessVoice |BusinessVoice |BusinessVoice |BusinessVoice |
|VoiceRoutingPolicy|Tem um valor|Tem um valor|Tem um valor|Não disponível|
|OnlineVoiceRoutingPolicy|$Null|$Null|$Null|Tem um valor|
|TeamsUpgradePolicy<sup>1</sup>|TeamsOnly, SfBOnly|$Null|$Null|TeamsOnly|
|TeamsCallingPolicy </br>AllowPrivateCalling|Verdadeiro|N/D|N/D|Verdadeiro|
|TeamsCallingPolicy </br>AllowGroupCalling|Verdadeiro|N/D|N/D|Verdadeiro|
||||||

<sup>1</sup> Escolher o modo certo do TeamsUpgradePolicy depende do cenário. Leia sobre a experiência de voz nos diferentes modos em[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md).

Como parte desse esforço, a Microsoft atualizou recentemente o "centro de administração do Microsoft Teams" (também conhecido como Modern Portal) para aplicar o novo modelo de gerenciamento com base nos modos de coexistência. No Modern Portal, configurar o TeamsUpgradePolicy agora também configurará automaticamente o TeamsInteropPolicy como valor consistente, de modo que o TeamsInteropPolicy não seja mais exposto na interface do usuário. No entanto, os administradores usando o PowerShell ainda devem configurar o TeamsUpgradePolicy e o TeamsInteropPolicy juntos para garantir a circulação adequada. Após a transição para o TeamsUpgradePolicy ser concluída, não será mais necessário definir o TeamsInteropPolicy.

Para obter mais informações, confira[Orientações de Migração e Interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md).

## <a name="migrating-from-calling-plans"></a>Migrar de planos de chamadas

Para obter mais informações sobre como migrar de Planos de Chamadas, consulte:

- [Configurar Planos de Chamadas](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [Usuário Set-CsOnlineVoice](/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [Get-CsOnlineLisLocation](/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
É recomendável remover o plano de licenciamento configurado anteriormente da seguinte maneira:
 
```powershell
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Migração do Sistema de Telefonia do Office 365 com conectividade PSTN local no Skype for Business Server

Para obter mais informações sobre como migrar do Sistema de Telefonia com conectividade PSTN local no Skype for Business Server, confira o seguinte:

- [Planejamento](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [Implantação](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

É recomendável remover as informações de roteamento de voz configuradas anteriormente da seguinte maneira:

```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
> [!NOTE]
> Se um CsVoiceRoutingPolicy global estiver configurado, é recomendável remover quaisquer usos PSTN associados a essa política global. 

## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a>Migração do Sistema de Telefonia do Office 365 com conectividade PSTN local através da Edição Cloud Connector 

> [!Important]
> O Cloud Connector Edition se aposentará em 31 de julho de 2021 junto com Skype for Business Online. Depois que sua organização tiver sido atualizada para Teams, saiba como conectar sua rede de telefonia local ao Teams usando [Roteamento Direto](direct-routing-landing-page.md).

Para obter mais informações sobre como migrar do Sistema de Telefonia com conectividade PSTN local via Cloud Conector, confira o seguinte:

- [Planejamento](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [Implantação](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [Configuração do usuário](/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

É recomendável remover as informações de roteamento de voz configuradas anteriormente da seguinte maneira:
 
```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a>Links relacionados

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[Get-CsTeamsUpgradePolicy](/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[New-CsTeamsUpgradePolicy](/powershell/module/skype/New-CsTeamsUpgradePolicy)

[Remove-CsTeamsUpgradePolicy](/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[Set-CsTeamsUpgradePolicy](/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[Get-CsTeamsUpgradeConfiguration](/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[Set-CsTeamsUpgradeConfiguration](/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)