---
title: Implantações locais de várias florestas do Sistema de Sala do Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: Leia este tópico para saber como implantar o Sistema de Sala do Skype em um ambiente local de várias florestas.
ms.openlocfilehash: 168244033a681b9aa9dc6e4c9697b7e3c7e89127
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805741"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a><span data-ttu-id="9d916-103">Implantações locais de várias florestas do Sistema de Sala do Skype</span><span class="sxs-lookup"><span data-stu-id="9d916-103">Skype Room System multiple forest on-premises deployments</span></span>
 
<span data-ttu-id="9d916-104">Leia este tópico para saber como implantar o Sistema de Sala do Skype em um ambiente local de várias florestas.</span><span class="sxs-lookup"><span data-stu-id="9d916-104">Read this topic to learn how to deploy Skype Room System in a multiple forest on-premises environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9d916-105">Para implantar em várias florestas, o Sistema de Sala do Skype requer o Exchange Server 2013 CU6 lançado em 26 de agosto de 2014.</span><span class="sxs-lookup"><span data-stu-id="9d916-105">In order to deploy in multiple forests, Skype Room System requires Exchange Server 2013 CU6 released on August 26, 2014.</span></span> <span data-ttu-id="9d916-106">Evite re-usar uma caixa de correio existente para o Sistema de Sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="9d916-106">Avoid re-using an existing mailbox for Skype Room System.</span></span> <span data-ttu-id="9d916-107">Use uma nova caixa de correio de recurso (excluir a caixa de correio antiga e re-criar) para o Sistema de Sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="9d916-107">Use a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="9d916-108">Para restaurar as reuniões perdidas pela exclusão da caixa de correio, consulte [Conectar ou restaurar uma caixa de correio excluída.](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9d916-108">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="9d916-109">Depois de criar a caixa de correio, você pode Set-CalendarProcessing para configurar a caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="9d916-109">After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox.</span></span> <span data-ttu-id="9d916-110">Consulte as etapas 3 a 6 em Implantações locais de floresta única para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="9d916-110">Refer to steps 3 through 6 under Single forest on-premises deployments for more details.</span></span> <span data-ttu-id="9d916-111">Depois de criar uma caixa de correio de Recurso do Exchange para o Sistema de Sala do Skype, habilita a conta do Skype for Business seguindo as etapas em Habilitar contas do Sistema de Sala do Skype para o Skype for Business em implantações locais de floresta única.</span><span class="sxs-lookup"><span data-stu-id="9d916-111">After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.</span></span>
  
## <a name="option-1-create-a-new-resource-mailbox"></a><span data-ttu-id="9d916-112">Opção 1: Criar uma nova caixa de correio de recurso</span><span class="sxs-lookup"><span data-stu-id="9d916-112">Option 1: Create a new resource mailbox</span></span>

<span data-ttu-id="9d916-113">Para implantar o Sistema de Sala do Skype em um ambiente de várias florestas:</span><span class="sxs-lookup"><span data-stu-id="9d916-113">To deploy Skype Room System in a multi-forest environment:</span></span>
  
1. <span data-ttu-id="9d916-114">Criar um Usuário Vinculado (LinkedRoomTest) no Active Directory (Floresta de Autenticação).</span><span class="sxs-lookup"><span data-stu-id="9d916-114">Create a Linked User (LinkedRoomTest) in Active Directory (Authentication Forest).</span></span>
    
2. <span data-ttu-id="9d916-115">Execute os seguintes comandos no Shell de Gerenciamento do Exchange Server:</span><span class="sxs-lookup"><span data-stu-id="9d916-115">Run the following commands in the Exchange Server Management Shell:</span></span>
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a><span data-ttu-id="9d916-116">Opção 2: Alterar uma caixa de correio de sala existente para a caixa de correio de recurso do Sistema de Sala do Skype (vinculado)</span><span class="sxs-lookup"><span data-stu-id="9d916-116">Option 2: Change an existing room mailbox to Skype Room System (linked) resource mailbox</span></span>

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


