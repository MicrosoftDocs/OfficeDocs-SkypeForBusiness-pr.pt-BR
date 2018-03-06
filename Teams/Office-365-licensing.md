---
title: "Licença do Office 365 para o Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen, ninadara
description: "Conheça as diferentes licenças do Office 365, quais delas habilitam os usuários para o Microsoft Teams e como habilitá-las ou desabilitá-las."
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 868b84d48a85464dc0d9b1890354dad42d9cb068
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2018
---
<a name="office-365-licensing-for-microsoft-teams"></a>Licença do Office 365 para o Microsoft Teams
========================================

As seguintes assinaturas do Office 365 habilitam os usuários para o Microsoft Teams:

|Planos para pequenas empresas  |Planos empresariais  |Planos educacionais  |
|---------|---------|---------|
|Office 365 Business Essentials     |Office 365 Enterprise E1         |Office 365 Education         |
|Office 365 Business Premium     |Office 365 Enterprise E3         |Office 365 Education Plus         |
|     |Office 365 Enterprise E4 (desativado)         |Office 365 Education E3 (desativado)         |
|     |Office 365 Enterprise E5         |Office 365 Education E5   
      |Office 365 Enterprise F1 |  |

> [!NOTE]
> O Microsoft Teams também está disponível para organizações sem fins lucrativos. Não há suporte no momento para licenças governamentais, mas estão sendo examinadas para suporte futuro.
        


Em termos de funcionalidades básicas do Microsoft Teams, não há diferenças entre as diversas assinaturas do Office 365. A disponibilidade de recursos de conformidade depende do nível correto da assinatura. Para saber mais, leia [Visão geral de segurança e conformidade no Microsoft Teams](security-compliance-overview.md).

Todos os planos de assinatura suportados são qualificados para acessar o cliente Web, os clientes de desktop e aplicativos móveis do Microsoft Teams.

O Microsoft Teams não está disponível como um serviço autônomo.

<a name="teams-license"></a>Licença do Microsoft Teams
-------------

Por padrão, a licença do Microsoft Teams está habilitada para todos os usuários com assinaturas qualificadas do Office 365.

![Captura de tela das configurações na seção de licenças do centro de administração do Office 365, mostrando o Microsoft Teams como Habilitado.](media/Understand_Office_365_Licensing__for_Microsoft_Teams_image2.png)


O Teams pode ser ativado ou desativado para um tipo de licença inteira em uma organização e está ativado, por padrão, para todos os tipos de licença, exceto para usuários convidados.

> [!IMPORTANT]
> Você não pode ativar o Microsoft Teams apenas para parte de um tipo de licença usando a opção Teams no Centro de administração do Office 365. Se você deseja ativar o Teams para algumas pessoas de sua organização e desativá-lo para outras pessoas (por exemplo, se você está planejando um piloto do Teams para um grupo específico de usuários), ative a opção de licença do Teams para todos e, em seguida, desative-a individualmente para os usuários desejados.

![Captura de tela da configuração de tipo de usuário/licença do Teams na seção de licença do Centro de administração do Office 365, mostrando o Microsoft Teams como Ativado.](media/Understand_Office_365_Licensing__for_Microsoft_Teams_image3.png)


> [!TIP]
> A habilitação e desabilitação do Microsoft Teams como uma licença de carga de trabalho pelo PowerShell é realizada da mesma forma que com qualquer outra carga de trabalho. O nome do plano de serviço é TEAMS1 for Microsoft Teams. (Consulte mais informações em [Desabilitar o acesso aos serviços com o PowerShell do Office 365](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell).)

**Exemplo:** Segue um exemplo rápido de como desabilitar o Microsoft Teams para todos com um tipo de licença específico. Você precisa fazer isso primeiro e depois habilitá-lo individualmente para os usuários que devem ter acesso para fins de piloto.

Para exibir os tipos de assinatura que você tem na organização, use este comando:

      Get-MsolAccountSku

Preencha o nome do seu plano, quen inclui o nome da organização e o plano da escola (como ContosoSchool:ENTERPRISEPACK_STUDENT) e execute estes comandos:

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
Para desabilitar o Microsoft Teams para todos os usuários com uma licença ativa do plano nomeado, execute este comando:

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x