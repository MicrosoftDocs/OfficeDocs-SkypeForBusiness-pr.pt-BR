---
title: 'Lync Server 2013: telefones de área comuns'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Common area phones
ms:assetid: d63bb3de-154e-4347-9251-9fa94e7d593a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994076(v=OCS.15)
ms:contentKeyID: 51803987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 179d6a0102e62a081846a14981ed70294432ed44
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-area-phones-in-lync-server-2013"></a><span data-ttu-id="4fdb5-102">Telefones de área comuns no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fdb5-102">Common area phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4fdb5-103">_**Tópico da última modificação:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="4fdb5-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="4fdb5-104">Os telefones de área comuns são telefones IP que não estão associados a um usuário individual.</span><span class="sxs-lookup"><span data-stu-id="4fdb5-104">Common area phones are IP phones that are not associated with an individual user.</span></span> <span data-ttu-id="4fdb5-105">Em vez de estar localizado no escritório de alguém, os telefones de área comuns geralmente estão localizados em prédio "lobbies", lanchonetes, descansos de funcionários, salas de reunião e outros locais onde um grande número de pessoas provavelmente coletará.</span><span class="sxs-lookup"><span data-stu-id="4fdb5-105">Instead of being located in someone’s office, common area phones are typically located in building lobbies, cafeterias, employee lounges, meeting rooms, and other locations where a large number of people are likely to gather.</span></span> <span data-ttu-id="4fdb5-106">Ao contrário de outros telefones no Lync Server, que são normalmente mantidos por meio de políticas de voz e planos de discagem que são atribuídos a usuários individuais, os telefones de área comuns não têm usuários individuais atribuídos a eles.</span><span class="sxs-lookup"><span data-stu-id="4fdb5-106">Unlike other phones in Lync Server, which are typically maintained by using voice policies and dial plans that are assigned to individual users, common area phones do not have individual users assigned to them.</span></span> <span data-ttu-id="4fdb5-107">Isso significa que elas devem ser gerenciadas de maneira diferente dos outros telefones.</span><span class="sxs-lookup"><span data-stu-id="4fdb5-107">This means that they must be managed differently than your other phones.</span></span>

<span data-ttu-id="4fdb5-108">Para gerenciar telefones de área comuns, crie objetos de contato dos serviços de domínio Active Directory para todos os telefones comuns que, como contas de usuário, podem ser atribuídos a políticas e planos de voz.</span><span class="sxs-lookup"><span data-stu-id="4fdb5-108">To manage common area phones, you create Active Directory Domain Services contact objects for all your common area phones that, like user accounts, can be assigned policies and voice plans.</span></span> <span data-ttu-id="4fdb5-109">Essa abordagem permite que você mantenha o controle sobre telefones comuns de área, embora esses telefones não estejam associados a um usuário individual.</span><span class="sxs-lookup"><span data-stu-id="4fdb5-109">This approach enables you to maintain control over common area phones, even though those phones are not associated with an individual user.</span></span>

<span data-ttu-id="4fdb5-110">Use os tópicos desta seção para saber como criar objetos de contato para telefones celulares comuns, modificá-los e excluí-los e configurar e exibir informações de configuração sobre os telefones celulares comuns na sua implantação.</span><span class="sxs-lookup"><span data-stu-id="4fdb5-110">Use the topics in this section to learn how to create contact objects for common area phones, modify and delete them, and configure and view configuration information about the common area phones in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4fdb5-111">Você tem três opções para telefones celulares comuns: o Aastra 6721ip Common de área comum, o telefone IP HP 4110 e o telefone de área comum de IP do CX500 Polycom.</span><span class="sxs-lookup"><span data-stu-id="4fdb5-111">You have three options for common area phones: the Aastra 6721ip common area phone, the HP 4110 IP Phone, and the Polycom CX500 IP common area phone.</span></span> <span data-ttu-id="4fdb5-112">O telefone de conferência IP do Polycom CX3000 é outro telefone de área comum da variante.</span><span class="sxs-lookup"><span data-stu-id="4fdb5-112">The Polycom CX3000 IP conferencing phone is another variant common area phone.</span></span> <span data-ttu-id="4fdb5-113">No entanto, ele deve ser usado em salas de conferência.</span><span class="sxs-lookup"><span data-stu-id="4fdb5-113">However, it is intended for use in conference rooms.</span></span> <span data-ttu-id="4fdb5-114">Para obter detalhes sobre telefones de área comuns, consulte a seção de telefones da área comum da <A href="http://technet.microsoft.com/en-us/library/gg398958(v=ocs.14).aspx">escolha de novos dispositivos</A>.</span><span class="sxs-lookup"><span data-stu-id="4fdb5-114">For details about common area phones, see the Common Area Phones section of <A href="http://technet.microsoft.com/en-us/library/gg398958(v=ocs.14).aspx">Choosing New Devices</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4fdb5-115">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="4fdb5-115">In This Section</span></span>

  - [<span data-ttu-id="4fdb5-116">Exibir informações de telefone de área comum no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fdb5-116">View common area phone information in Lync Server 2013</span></span>](lync-server-2013-view-common-area-phone-information.md)

  - [<span data-ttu-id="4fdb5-117">Criar ou modificar um objeto de contato de telefone de área comum no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fdb5-117">Create or modify a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="4fdb5-118">Habilitar ou desabilitar o hot desk no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fdb5-118">Enable or disable hot desking in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-hot-desking.md)

  - [<span data-ttu-id="4fdb5-119">Excluir um objeto de contato de telefone de área comum no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fdb5-119">Delete a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-delete-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="4fdb5-120">Atribuir políticas no Lync Server 2013 a um telefone de área comum</span><span class="sxs-lookup"><span data-stu-id="4fdb5-120">Assign policies in Lync Server 2013 to a common area phone</span></span>](lync-server-2013-assign-policies-to-a-common-area-phone.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

