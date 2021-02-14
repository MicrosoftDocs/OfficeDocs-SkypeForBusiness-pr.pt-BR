---
title: Verificar Replicação de Partição do Esquema
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para verificar se a extensão do esquema foi replicada com êxito em sua floresta dos Serviços de Domínio Active Directory, faça o seguinte:'
ms.openlocfilehash: 4e4bfdf4fb50366f831f029d8f331551ba906969
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801561"
---
# <a name="verify-replication-of-schema-partition"></a><span data-ttu-id="c6cff-103">Verificar a Replicação de Partição do Esquema</span><span class="sxs-lookup"><span data-stu-id="c6cff-103">Verify Replication of Schema Partition</span></span>
 
<span data-ttu-id="c6cff-104">Para verificar se a extensão do esquema foi replicada com êxito em sua floresta dos Serviços de Domínio Active Directory, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c6cff-104">To verify that the schema extension have been successfully replicated in your Active Directory Domain Services forest, do the following:</span></span>
  
1. <span data-ttu-id="c6cff-105">Faça logoff em um controlador de domínio (que não seja o controlador de domínio que detém a função mestra de esquema) em sua floresta dos Serviços de Domínio Active Directory, onde as extensões de esquema foram aplicadas como membro do grupo Administradores de Empresa.</span><span class="sxs-lookup"><span data-stu-id="c6cff-105">Log on to a domain controller (other than the domain controller that holds the schema master role) in your Active Directory Domain Services forest, where the schema extensions were applied as a member of the Enterprise Admins group.</span></span>
    
2. <span data-ttu-id="c6cff-106">Abra o Editor ADSI: clique em **Iniciar**, em **Ferramentas Administrativas** e clique em **Editor ADSI**.</span><span class="sxs-lookup"><span data-stu-id="c6cff-106">Open ADSI Edit: Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c6cff-107">Como alternativa, clique em **Iniciar**, em **Executar**, digite **adsiedit.msc** para iniciar o Editor ADSI.</span><span class="sxs-lookup"><span data-stu-id="c6cff-107">Alternatively, click **Start**, then click **Run**, type **adsiedit.msc** to start ADSI Edit.</span></span>
  
3. <span data-ttu-id="c6cff-108">Na árvore Console de Gerenciamento Microsoft (MMC) clique em Edição ADSI, se já não está selecionado.</span><span class="sxs-lookup"><span data-stu-id="c6cff-108">In the Microsoft Management Console (MMC) tree, if it is not already selected, click ADSI Edit.</span></span>
    
4. <span data-ttu-id="c6cff-109">No menu **Ação**, clique em **Conectar-se a**.</span><span class="sxs-lookup"><span data-stu-id="c6cff-109">On the **Action** menu, click **Connect to**.</span></span>
    
5. <span data-ttu-id="c6cff-110">Na caixa de diálogo **Configurações de Conexão** em **Selecione um Contexto de Nomenclatura bem conhecido**, selecione **Esquema** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6cff-110">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
6. <span data-ttu-id="c6cff-p101">No contêiner de esquema, procure por CN=ms-RTC-SIP-SchemaVersion. Se esse objeto existir e o valor do atributo **rangeUpper** for 1150 e o valor do atributo **rangeLower** for 3, o esquema terá sido atualizado e replicado com êxito. Se esse objeto não existir ou se os valores dos atributos **rangeUpper** e **rangeLower** não seguirem a especificação, o esquema não terá sido modificado ou replicado.</span><span class="sxs-lookup"><span data-stu-id="c6cff-p101">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion. If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated. If this object does not exist or if the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c6cff-114">Se a sua verificação da replicação ainda não mostrar uma replicação bem-sucedida, aguarde aproximadamente 15 minutos e verifique novamente.</span><span class="sxs-lookup"><span data-stu-id="c6cff-114">If your check of the replication of the schema does not yet show a successful replication, wait approximately 15 minutes and then check again.</span></span> <span data-ttu-id="c6cff-115">A replicação do Active Directory baseia-se em um modelo de consistência solta e pode ocorrer alguma latência de replicação, com base em vários fatores no servidor e na infraestrutura.</span><span class="sxs-lookup"><span data-stu-id="c6cff-115">Active Directory replication is based on a loose consistency model and some replication latency can occur, based on a number of factors in the server and infrastructure.</span></span> 
  

