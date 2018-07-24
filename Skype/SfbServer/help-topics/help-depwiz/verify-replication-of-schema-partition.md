---
title: Verificar a replicação de partição do esquema
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: 'Para verificar se a extensão do esquema foi replicada com êxito em sua floresta do Active Directory Domain Services, faça o seguinte:'
ms.openlocfilehash: 632553c382e8475cbe3d0f84dafb624c1f055d79
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20992073"
---
# <a name="verify-replication-of-schema-partition"></a><span data-ttu-id="88d9f-103">Verificar a replicação de partição do esquema</span><span class="sxs-lookup"><span data-stu-id="88d9f-103">Verify Replication of Schema Partition</span></span>
 
<span data-ttu-id="88d9f-104">Para verificar se a extensão do esquema foi replicada com êxito em sua floresta do Active Directory Domain Services, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="88d9f-104">To verify that the schema extension have been successfully replicated in your Active Directory Domain Services forest, do the following:</span></span>
  
1. <span data-ttu-id="88d9f-105">Faça logon um controlador de domínio (que não seja um controlador de domínio que detém a função de mestre de esquema) em sua floresta do Active Directory Domain Services, onde as extensões de esquema foram aplicadas como membro do grupo Administradores de empresa.</span><span class="sxs-lookup"><span data-stu-id="88d9f-105">Log on to a domain controller (other than the domain controller that holds the schema master role) in your Active Directory Domain Services forest, where the schema extensions were applied as a member of the Enterprise Admins group.</span></span>
    
2. <span data-ttu-id="88d9f-106">Abrir o ADSI Edit: Clique em **Iniciar**, clique em **Ferramentas administrativas**e, em seguida, clique em Editor **ADSI**.</span><span class="sxs-lookup"><span data-stu-id="88d9f-106">Open ADSI Edit: Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="88d9f-107">Como alternativa, clique em **Iniciar**, clique em **Executar**, tipo **ADSIEdit. msc** para iniciar o ADSI Edit.</span><span class="sxs-lookup"><span data-stu-id="88d9f-107">Alternatively, click **Start**, then click **Run**, type **adsiedit.msc** to start ADSI Edit.</span></span>
  
3. <span data-ttu-id="88d9f-108">Na árvore do Console de gerenciamento Microsoft (MMC), se não ainda estiver selecionada, clique em Editor ADSI.</span><span class="sxs-lookup"><span data-stu-id="88d9f-108">In the Microsoft Management Console (MMC) tree, if it is not already selected, click ADSI Edit.</span></span>
    
4. <span data-ttu-id="88d9f-109">No menu **Ação**, clique em **Conectar-se a**.</span><span class="sxs-lookup"><span data-stu-id="88d9f-109">On the **Action** menu, click **Connect to**.</span></span>
    
5. <span data-ttu-id="88d9f-110">Na caixa de diálogo **Configurações de conexão** em **Selecione um Contexto de nomenclatura bem conhecido**, selecione **Esquema** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="88d9f-110">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
6. <span data-ttu-id="88d9f-111">No contêiner de esquema, procure por CN=ms-RTC-SIP-SchemaVersion.</span><span class="sxs-lookup"><span data-stu-id="88d9f-111">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="88d9f-112">Se esse objeto existir e o valor do atributo **rangeUpper** for 1150 e o valor do atributo **rangeLower** é 3, em seguida, o esquema foi com êxito atualizado e replicado.</span><span class="sxs-lookup"><span data-stu-id="88d9f-112">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="88d9f-113">Se este objeto não existir ou se os valores dos atributos **rangeUpper** e **rangeLower** não são como especificado, em seguida, o esquema não foi modificado ou não foi replicado.</span><span class="sxs-lookup"><span data-stu-id="88d9f-113">If this object does not exist or if the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>
    
> [!NOTE]
> <span data-ttu-id="88d9f-114">Se a sua seleção da replicação do esquema não mostrar uma replicação bem-sucedida ainda, aguarde aproximadamente 15 minutos e verifique novamente.</span><span class="sxs-lookup"><span data-stu-id="88d9f-114">If your check of the replication of the schema does not yet show a successful replication, wait approximately 15 minutes and then check again.</span></span> <span data-ttu-id="88d9f-115">Replicação do Active Directory é baseada em um modelo de consistência ampliada e alguns latência de replicação pode ocorrer, com base em vários fatores no servidor e infra-estrutura.</span><span class="sxs-lookup"><span data-stu-id="88d9f-115">Active Directory replication is based on a loose consistency model and some replication latency can occur, based on a number of factors in the server and infrastructure.</span></span> 
  

