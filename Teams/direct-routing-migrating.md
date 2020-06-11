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
ms.openlocfilehash: 11240c3a1067885dbf34499a4e131185acccbf52
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691357"
---
# <a name="migrate-to-direct-routing"></a>Migrar para o Roteamento Direto

Este artigo descreve o que é necessário para migrar para o Roteamento Direto de uma perspectiva de configuração do Skype for Business Online e do Teams. Este artigo aborda a migração dos seguintes sistemas: 
 
- Sistema telefônico com planos de chamada (para Teams e Skype for Business online) 
- Sistema telefônico com conectividade PSTN local no Skype for Business Server (para Skype for Business online)  
- Sistema telefônico com conectividade PSTN local usando o Cloud Connector Edition (para Skype for Business online)


Além dessas etapas de configuração, também é necessário configurar o Controlador de Borda de Sessão (SBC) para direcionar as chamadas para a nova rota. Isso está fora do escopo deste documento. Para obter mais informações, consulte a documentação do seu fornecedor de SBC.  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a>Provisionamento de usuário estado final para várias opções de conectividade PSTN 

A tabela a seguir mostra o estado final de um usuário provisionado para as opções de conectividade PSTN selecionadas com o sistema telefônico. São exibidos somente os atributos relevantes para voz.

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

<sup>1</sup> escolher o modo correto do TeamsUpgradePolicy depende do cenário. Leia sobre a experiência de voz nos diferentes modos em[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md).

Como parte desse esforço, a Microsoft atualizou recentemente o "centro de administração do Microsoft Teams" (também conhecido como Modern Portal) para aplicar o novo modelo de gerenciamento com base nos modos de coexistência. No Modern Portal, configurar o TeamsUpgradePolicy agora também configurará automaticamente o TeamsInteropPolicy como valor consistente, de modo que o TeamsInteropPolicy não seja mais exposto na interface do usuário. No entanto, os administradores usando o PowerShell ainda devem configurar o TeamsUpgradePolicy e o TeamsInteropPolicy juntos para garantir a circulação adequada. Após a transição para o TeamsUpgradePolicy ser concluída, não será mais necessário definir o TeamsInteropPolicy.

Para obter mais informações, confira[Orientações de Migração e Interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md).

## <a name="migrating-from-calling-plans"></a>Migrar de planos de chamadas

Para obter mais informações sobre como migrar de Planos de Chamadas, consulte:

- [Configurar Planos de Chamadas](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [Usuário Set-CsOnlineVoice](https://docs.microsoft.com/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [Get-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
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

- [Planejamento](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [Implantação](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

É recomendável remover as informações de roteamento de voz configuradas anteriormente da seguinte maneira:

```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
> [!NOTE]
> Se uma CsVoiceRoutingPolicy global estiver configurada, recomendamos que você remova todos os usos de PSTN associados a essa política global. 

## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a>Migração do Sistema de Telefonia do Office 365 com conectividade PSTN local através da Edição Cloud Connector 

Para obter mais informações sobre como migrar do Sistema de Telefonia com conectividade PSTN local via Cloud Conector, confira o seguinte:

- [Planejamento](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [Implantação](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [Configuração do usuário](https://docs.microsoft.com/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

É recomendável remover as informações de roteamento de voz configuradas anteriormente da seguinte maneira:
 
```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a>Links relacionados

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[New-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsUpgradePolicy)

[Remove-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[Set-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)

