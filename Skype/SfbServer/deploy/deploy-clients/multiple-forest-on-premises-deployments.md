---
title: Implantações locais de várias florestas do Sistema de Salas do Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: Leia este tópico para saber como implantar o Sistema de Salas do Skype em um ambiente local de várias florestas.
ms.openlocfilehash: 507040a1d8274817e7a4a0780135ee8f6642c77c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219413"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a><span data-ttu-id="169a2-103">Implantações locais de várias florestas do Sistema de Salas do Skype</span><span class="sxs-lookup"><span data-stu-id="169a2-103">Skype Room System multiple forest on-premises deployments</span></span>
 
<span data-ttu-id="169a2-104">Leia este tópico para saber como implantar o Sistema de Salas do Skype em um ambiente local de várias florestas.</span><span class="sxs-lookup"><span data-stu-id="169a2-104">Read this topic to learn how to deploy Skype Room System in a multiple forest on-premises environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="169a2-105">Para implantar em várias florestas, o sistema de sala Skype exige Exchange Server 2013 CU6 lançada em 26 de agosto de 2014.</span><span class="sxs-lookup"><span data-stu-id="169a2-105">In order to deploy in multiple forests, Skype Room System requires Exchange Server 2013 CU6 released on August 26, 2014.</span></span> <span data-ttu-id="169a2-106">Evite reutilizando uma caixa de correio existente para o sistema de sala Skype.</span><span class="sxs-lookup"><span data-stu-id="169a2-106">Avoid re-using an existing mailbox for Skype Room System.</span></span> <span data-ttu-id="169a2-107">Usar um novo (antiga da caixa de correio de excluir e recriar) caixa de correio de recurso para o sistema de sala Skype.</span><span class="sxs-lookup"><span data-stu-id="169a2-107">Use a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="169a2-108">Para restaurar as reuniões perdidas, excluindo a caixa de correio, consulte [Connect ou restauração uma caixa de correio excluída](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="169a2-108">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="169a2-109">Após a criação da caixa de correio, você pode utilizar Set-CalendarProcessing para configurar a caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="169a2-109">After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox.</span></span> <span data-ttu-id="169a2-110">Consulte as etapas de 3 a 6 sob implantações locais da floresta única para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="169a2-110">Refer to steps 3 through 6 under Single forest on-premises deployments for more details.</span></span> <span data-ttu-id="169a2-111">Depois de criar uma caixa de correio de recurso do Exchange para o sistema de sala do Skype, habilite a conta do Skype para os negócios seguindo as etapas em habilitando contas de sistema do Skype sala para Skype para negócios em implantações em instalações de floresta única.</span><span class="sxs-lookup"><span data-stu-id="169a2-111">After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.</span></span>
  
## <a name="option-1-create-a-new-resource-mailbox"></a><span data-ttu-id="169a2-112">Opção 1: criar uma nova caixa de correio de recursos</span><span class="sxs-lookup"><span data-stu-id="169a2-112">Option 1: Create a new resource mailbox</span></span>

<span data-ttu-id="169a2-113">Para implantar o sistema de sala do Skype em um ambiente de várias floresta:</span><span class="sxs-lookup"><span data-stu-id="169a2-113">To deploy Skype Room System in a multi-forest environment:</span></span>
  
1. <span data-ttu-id="169a2-114">Criar um Usuário vinculado (LinkedRoomTest) no Active Directory (Floresta de Autenticação).</span><span class="sxs-lookup"><span data-stu-id="169a2-114">Create a Linked User (LinkedRoomTest) in Active Directory (Authentication Forest).</span></span>
    
2. <span data-ttu-id="169a2-115">Execute os seguintes comandos do Shell de Gerenciamento do Exchange Server:</span><span class="sxs-lookup"><span data-stu-id="169a2-115">Run the following commands in the Exchange Server Management Shell:</span></span>
    
   ```
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a><span data-ttu-id="169a2-116">Opção 2: Alterar uma caixa de correio de sala existente à caixa de correio de recurso (vinculado) de sistema de sala do Skype</span><span class="sxs-lookup"><span data-stu-id="169a2-116">Option 2: Change an existing room mailbox to Skype Room System (linked) resource mailbox</span></span>

```
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


