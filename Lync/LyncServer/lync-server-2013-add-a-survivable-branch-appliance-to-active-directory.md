---
title: 'Lync Server 2013: Adicionar um Aplicativo de Filial Persistente ao Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add a Survivable Branch Appliance to Active Directory
ms:assetid: 3e63507c-d60b-40ec-8bbe-586b1d707c3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425906(v=OCS.15)
ms:contentKeyID: 48183938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dc057318a0d241a28b8529802ea9f2016a1f5b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a><span data-ttu-id="6fdc6-102">Adicionar um Aplicativo de Filial Persistente ao Active Directory no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fdc6-102">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fdc6-103">_**Tópico da última modificação:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="6fdc6-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="6fdc6-104">Se você planeja implantar um aparelho de ramificação sobreviventes, será necessário adicionar o aparelho de ramificação sobreviventes aos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6fdc6-104">If you plan to deploy a Survivable Branch Appliance, you must add the Survivable Branch Appliance to Active Directory Domain Services.</span></span> <span data-ttu-id="6fdc6-105">Execute este procedimento no site central.</span><span class="sxs-lookup"><span data-stu-id="6fdc6-105">Perform this procedure at the central site.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6fdc6-106">Execute este procedimento apenas se você estiver implantando um aparelho de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="6fdc6-106">Perform this procedure only if you are deploying a Survivable Branch Appliance.</span></span> <span data-ttu-id="6fdc6-107">Não o execute se você estiver implantando um servidor de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="6fdc6-107">Do not perform it if you are deploying a Survivable Branch Server.</span></span>



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a><span data-ttu-id="6fdc6-108">Para adicionar um aparelho de ramificação sobreviventes aos serviços de domínio do Active Directory</span><span class="sxs-lookup"><span data-stu-id="6fdc6-108">To add an Survivable Branch Appliance to Active Directory Domain Services</span></span>

1.  <span data-ttu-id="6fdc6-109">Faça logon em um servidor membro como membro do grupo Administradores da empresa.</span><span class="sxs-lookup"><span data-stu-id="6fdc6-109">Log on to a member server as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="6fdc6-110">Clique em **Iniciar**, em **Ferramentas administrativas**e em **usuários e computadores do Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="6fdc6-110">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="6fdc6-111">No menu **ações** , clique em **novo** e, em seguida, clique em **computador**.</span><span class="sxs-lookup"><span data-stu-id="6fdc6-111">On the **Actions** menu, click **New** and then click **Computer**.</span></span>

4.  <span data-ttu-id="6fdc6-112">Na caixa de diálogo **novo objeto-computador** , digite um nome para o objeto de computador de aparelho de ramificação sobreviventes (por exemplo, BranchOffice1) e, em seguida, clique em **alterar**.</span><span class="sxs-lookup"><span data-stu-id="6fdc6-112">In the **New Object-Computer** dialog box, type in a name for the Survivable Branch Appliance computer object (for example, BranchOffice1), and then click **Change**.</span></span>

5.  <span data-ttu-id="6fdc6-113">Na caixa de diálogo **Selecionar usuário ou grupo** , adicione o grupo RTCUniversalSBATechnicians e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6fdc6-113">In the **Select User or Group** dialog box, add the RTCUniversalSBATechnicians group and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6fdc6-114">Um membro do grupo RTCUniversalSBATechnicians no site da filial adicionará esse dispositivo ao domínio mais tarde.</span><span class="sxs-lookup"><span data-stu-id="6fdc6-114">A member of the RTCUniversalSBATechnicians group at the branch site will add this device to the domain later.</span></span>

    
    </div>

6.  <span data-ttu-id="6fdc6-115">Clique em **OK** para salvar o objeto de computador de aparelho de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="6fdc6-115">Click **OK** to save the Survivable Branch Appliance computer object.</span></span>

7.  <span data-ttu-id="6fdc6-116">Clique em **Iniciar**, em **Ferramentas administrativas**e em **ADSI Editar**.</span><span class="sxs-lookup"><span data-stu-id="6fdc6-116">Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>

8.  <span data-ttu-id="6fdc6-117">Em **ADSI Edit**, clique com o botão direito do mouse no objeto de computador que você criou nas etapas anteriores e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="6fdc6-117">In **ADSI Edit**, right-click the computer object that you created in the previous steps, and then click **Properties**.</span></span>

9.  <span data-ttu-id="6fdc6-118">Na lista atributo, clique em \*\*\*\* servicePrincipalName e, em seguida, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6fdc6-118">In the attribute list, click **servicePrincipalName**, and then click **Edit**.</span></span>

10. <span data-ttu-id="6fdc6-119">No campo **valor para adicionar** \<, digite host/SBA FQDN\> em que \<SBA FQDN\> é o nome de domínio totalmente qualificado (FQDN) do seu aparelho de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="6fdc6-119">In the **Value to add** field, type HOST/\<SBA FQDN\> where \<SBA FQDN\> is the fully qualified domain name (FQDN) of your Survivable Branch Appliance.</span></span> <span data-ttu-id="6fdc6-120">Por exemplo, digite **host/BranchOffice1. contoso. com**.</span><span class="sxs-lookup"><span data-stu-id="6fdc6-120">For example, type **HOST/BranchOffice1.contoso.com**.</span></span>

11. <span data-ttu-id="6fdc6-121">Clique em **OK** para salvar a configuração do atributo **servicePrincipalName** e, em seguida, clique em **OK** para salvar as propriedades do objeto do computador.</span><span class="sxs-lookup"><span data-stu-id="6fdc6-121">Click **OK** to save the **servicePrincipalName** attribute setting, and then click **OK** to save the computer object properties.</span></span>

12. <span data-ttu-id="6fdc6-122">Em **usuários e computadores do Active Directory**, clique com o botão direito do mouse em **usuários**, clique em **novo**e, em seguida, clique em **usuário**.</span><span class="sxs-lookup"><span data-stu-id="6fdc6-122">In **Active Directory Users and Computers**, right-click **Users**, click **New**, and then click **User**.</span></span>

13. <span data-ttu-id="6fdc6-123">Insira informações no Assistente para criar uma conta de usuário de domínio para um técnico de appliance de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="6fdc6-123">Enter information into the wizard to create a domain user account for a Survivable Branch Appliance technician.</span></span>

14. <span data-ttu-id="6fdc6-124">Em **usuários e computadores do Active Directory**, clique em **usuários**, clique com o botão direito do mouse no objeto do usuário e, em seguida, clique em **Adicionar a um grupo**.</span><span class="sxs-lookup"><span data-stu-id="6fdc6-124">In **Active Directory Users and Computers**, click **Users**, right-click the user object, and then click **Add to a group**.</span></span>

15. <span data-ttu-id="6fdc6-125">Em **digite os nomes dos objetos a serem selecionados**, digite **RTCUniversalSBATechnicians**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6fdc6-125">In **Enter the object names to select**, type **RTCUniversalSBATechnicians**, and then click **OK**.</span></span>

16. <span data-ttu-id="6fdc6-126">Repita as etapas 12-15 para cada técnico de site de filial.</span><span class="sxs-lookup"><span data-stu-id="6fdc6-126">Repeat Steps 12-15 for each branch site technician.</span></span>

<span data-ttu-id="6fdc6-127">**Próxima etapa**: [adicionar sites de filiais à sua topologia no Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="6fdc6-127">**Next step**: [Add branch sites to your topology in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

