---
title: Atribuir políticas a grandes conjuntos de usuários na sua escola
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: saragava,karsmith
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar a atribuição de política em lote para atribuir políticas a grandes conjuntos de usuários em sua instituição educacional em grande parte para fins escolares remotos (teleescolares, tele-School).
f1keywords: ''
ms.openlocfilehash: 5e3ee25bf4fadea595fc224b2944a12c279f9c59
ms.sourcegitcommit: 92a278c0145798266ecbe052e645b2259bcbd62d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2020
ms.locfileid: "42892271"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a>Atribuir políticas a grandes conjuntos de usuários na sua escola

Você precisa dar aos alunos e professores acesso a diferentes recursos do Microsoft Teams? Você pode identificar rapidamente os usuários da sua organização por tipo de licença e, em seguida, atribuí-los à política apropriada. Este tutorial mostra como usar a [atribuição de política de lote](assign-policies.md#assign-a-policy-to-a-batch-of-users) para atribuir uma política de reunião a usuários em massa.

Lembre-se de que, no Teams, os usuários obtêm automaticamente a política global (padrão para toda a organização) para um tipo de política de equipe, a menos que você crie e atribua uma política personalizada. Como a população dos alunos costuma ser o maior conjunto de usuários e muitas vezes recebem as configurações mais restritivas, recomendamos que você faça o seguinte:

- Edite e aplique a política global (padrão para toda a organização) para restringir recursos para os alunos. 
- Crie uma política personalizada que permita recursos essenciais, como chat particular e agendamento de reunião e atribuir a política a seus funcionários e educadores.

Lembre-se de que a política global será aplicada a todos os usuários de sua escola até você criar uma política personalizada e atribuí-la a seus funcionários e professores.

Neste tutorial, os alunos receberão a política de reunião global e usaremos o PowerShell para atribuir uma política de reunião personalizada chamada EducatorMeetingPolicy à equipe e educadores em massa. Presumimos que você tenha editado a política global para personalizar as configurações de reunião para os alunos e criou uma política personalizada que define a experiência da reunião para funcionários e educadores.

![Captura de tela da página políticas de reunião no centro de administração do teams](media/edu-batch-policy-assignment.png)

Siga estas etapas para atribuir uma política de reunião personalizada a funcionários e professores em massa.

## <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a>Conectar-se ao módulo do Azure AD PowerShell para Graph e ao módulo do PowerShell do teams

Antes de executar as etapas deste artigo, você precisará instalar e se conectar ao módulo Azure AD PowerShell para Graph (para identificar os usuários por suas licenças atribuídas) e ao módulo do Microsoft Teams PowerShell (para atribuir as políticas a esses usuários).

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a>Instalar e conectar-se ao módulo do Azure AD PowerShell para Graph

Abra um prompt de comando do Windows PowerShell com privilégios elevados (execute o Windows PowerShell como administrador) e execute o seguinte procedimento para instalar o módulo do Azure Active Directory PowerShell para Graph.

```powershell
Install-Module -Name AzureAD
```

Execute o seguinte para se conectar ao Azure AD.

```powershell
Connect-AzureAD
```

Quando for solicitado, entre usando suas credenciais de administrador.

Para saber mais, consulte [conectar-se com o módulo do PowerShell do Azure Active Directory para Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Instalar e conectar-se ao módulo do PowerShell do Microsoft Teams

Execute o seguinte para instalar o [módulo do Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams). Verifique se você instalou a versão 1.0.5 ou posterior.

```powershell
Install-Module -Name MicrosoftTeams
```

Execute o seguinte para se conectar ao Microsoft Teams e iniciar uma sessão.

```powershell
Connect-MicrosoftTeams
```
Quando for solicitado, entre usando as mesmas credenciais de administrador usadas para se conectar ao Azure AD.

## <a name="identify-your-users"></a>Identifique seus usuários

Primeiro, execute o seguinte procedimento para identificar seus funcionários e professores por tipo de licença. Isso informa quais SKUs estão em uso em sua organização. Em seguida, você pode identificar os funcionários e professores que têm uma SKU com docente atribuída.

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

Que retorna:

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

Neste exemplo, a saída mostra que a licença doce SkuId é "e97c048c-37a4-45fb-ab50-922fbf07a370".

> [!NOTE]
> Para ver uma lista de SKUs educacionais e IDs de SKU, consulte referência sobre o [SKU educacional](sku-reference-edu.md).

Em seguida, executamos o seguinte para identificar os usuários que têm essa licença e reuni-los juntos.

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

## <a name="assign-a-policy-in-bulk"></a>Atribuir uma política em massa

Agora, atribuímos as políticas adequadas aos usuários em massa. O número máximo de usuários para os quais você pode atribuir ou atualizar políticas é de 20.000 de cada vez. Por exemplo, se você tiver mais de 20.000 funcionários e professores, será necessário enviar vários lotes.

> [!IMPORTANT]
> No momento, recomendamos que você atribua políticas em lotes de 5.000 usuários por vez. Durante esses horários de maior demanda, você pode enfrentar atrasos em tempos de processamento. Para minimizar o impacto dessas melhorias de processamento, sugerimos que você envie tamanhos de lote menores de até 5.000 usuários e envie cada lote somente após a conclusão da conclusão do anterior. Enviar lotes para fora do seu horário de trabalho normal também pode ajudar.

Execute o seguinte para atribuir a política de reunião chamada EducatorMeetingPolicy à sua equipe e educadores.

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> Para atribuir um tipo de política diferente em massa, como TeamsMessagingPolicy, você precisará mudar ```PolicyType``` para a política que está atribuindo e ```PolicyName``` para o nome da política.

## <a name="get-the-status-of-a-bulk-assignment"></a>Obter o status de uma atribuição em massa

Cada atribuição em massa retorna uma ID de operação, que você pode usar para acompanhar o andamento das tarefas de política ou identificar quaisquer falhas que possam ocorrer. Por exemplo, execute o seguinte:

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

Para exibir o status da atribuição de cada usuário na operação em lotes, execute o seguinte. Os ```UserState``` detalhes de cada usuário estão na propriedade.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

## <a name="assign-a-policy-in-bulk-if-you-have-more-than-20000-users"></a>Atribuir uma política em massa se você tiver mais de 20.000 usuários

Primeiro, execute o seguinte procedimento para ver quantas pessoas e professores você tem:

```powershell
$faculty.count
```

Em vez de fornecer toda a lista de IDs de usuário, execute o seguinte para especificar o primeiro 20.000 e, em seguida, o próximo 20.000 e assim por diante.

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

Você pode alterar o intervalo de IDs de usuário até chegar à lista completa de usuários. Por exemplo, insira ```$faculty[0..19999``` para o primeiro lote, use ```$faculty[20000..39999``` para o segundo lote, insira ```$faculty[40000..59999``` para o terceiro lote e assim por diante.

## <a name="get-the-policies-assigned-to-a-user"></a>Obter as políticas atribuídas a um usuário

Execute o seguinte para ver todas as políticas atribuídas a um usuário específico. O exemplo a seguir mostra como obter as políticas atribuídas ao hannah@contoso.com.

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a>Perguntas frequentes

**Quero ter certeza de que todos os usuários que são alunos, funcionários e professores recebem automaticamente licenças atribuídas. Como posso fazer isso?**

A equipe de produto do teams está trabalhando para dar suporte à atribuição de políticas a grupos de segurança. Nesse momento, você poderá criar grupos para seus alunos e professores e, em seguida, as políticas apropriadas a esses grupos. Observe que atribuições explícitas de usuários (como as políticas que você atribuiu usando este tutorial) substituirão as políticas herdadas de um grupo. Quando esse recurso tiver suporte, forneceremos mais instruções sobre como usar a atribuição de política para grupos e atualizar os usuários para garantir que eles recebam as políticas de grupo herdadas.

**Não estou familiarizado com o PowerShell para Teams. Onde posso saber mais?**

Consulte [visão geral do teams PowerShell](teams-powershell-overview.md).

## <a name="related-topics"></a>Tópicos relacionados

- [Atribuir políticas aos usuários](assign-policies.md)
- [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)