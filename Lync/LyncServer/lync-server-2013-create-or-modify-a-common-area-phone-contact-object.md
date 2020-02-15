---
title: 'Lync Server 2013: criar ou modificar um objeto de contato de telefone de área comum'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a common area phone Contact object
ms:assetid: eec33ad1-e4f2-49b2-91d6-d5a9d2e1714b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994083(v=OCS.15)
ms:contentKeyID: 51803995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 418001642f387caf67277f408d4eb19109c98936
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="e1c60-102">Criar ou modificar um objeto de contato de telefone de área comum no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1c60-102">Create or modify a common area phone Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1c60-103">_**Última modificação do tópico:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="e1c60-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="e1c60-104">Para criar objetos de contato dos serviços de domínio do Active Directory para todos os telefones de área comum, use o cmdlet **New-CsCommonAreaPhone** .</span><span class="sxs-lookup"><span data-stu-id="e1c60-104">To create Active Directory Domain Services contact objects for all your common area phones, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="e1c60-105">Este cmdlet pode criar novos objetos de contato para uso com telefones de área comum ou pode associar objetos de contato existentes a um novo telefone de área comum.</span><span class="sxs-lookup"><span data-stu-id="e1c60-105">This cmdlet can either create new contact objects for use with common area phones, or it can associate existing contact objects with a new common area phone.</span></span> <span data-ttu-id="e1c60-106">Para modificar as propriedades dos objetos de contato associados a telefones de área comum, use o cmdlet **set-CsCommonAreaPhone** .</span><span class="sxs-lookup"><span data-stu-id="e1c60-106">To modify the properties of the contact objects associated with common area phones, use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="e1c60-107">Os parâmetros opcionais para **set-CsCommonAreaPhone** permitem que você altere itens, como o nome de exibição do Active Directory do contato ou o URI (Uniform Resource Identifier) da linha associado ao telefone e habilite e desabilite a conta para uso com o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e1c60-107">Optional parameters for **Set-CsCommonAreaPhone** enable you to change items, such as the contact’s Active Directory display name or the line Uniform Resource Identifier (URI) associated with the phone, and enable and disable the account for use with Lync Server.</span></span> <span data-ttu-id="e1c60-108">Para obter detalhes sobre todas as modificações disponíveis, consulte a seção parâmetros em [set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone).</span><span class="sxs-lookup"><span data-stu-id="e1c60-108">For details about all the available modifications, see the Parameters section at [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone).</span></span> <span data-ttu-id="e1c60-109">Para obter detalhes sobre os parâmetros **New-CsCommonAreaPhone** , consulte [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).</span><span class="sxs-lookup"><span data-stu-id="e1c60-109">For details about **New-CsCommonAreaPhone** parameters, see [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).</span></span>

<span data-ttu-id="e1c60-110">Você pode executar esses dois cmdlets do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1c60-110">You can run these two cmdlets from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e1c60-111">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="e1c60-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a><span data-ttu-id="e1c60-112">Criando um objeto de contato de telefone de área comum</span><span class="sxs-lookup"><span data-stu-id="e1c60-112">Creating a common area phone contact object</span></span>

  - <span data-ttu-id="e1c60-113">Para criar um novo objeto de contato de telefone de área comum, use o cmdlet **New-CsCommonAreaPhone** .</span><span class="sxs-lookup"><span data-stu-id="e1c60-113">To create a new common area phone contact object, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="e1c60-114">No mínimo, você deve fornecer as seguintes informações ao criar um objeto de contato:</span><span class="sxs-lookup"><span data-stu-id="e1c60-114">At a minimum, you must supply the following information when creating a contact object:</span></span>
    
      - <span data-ttu-id="e1c60-115">**LineUri**: o número de telefone atribuído ao telefone de área comum.</span><span class="sxs-lookup"><span data-stu-id="e1c60-115">**LineUri**: The telephone number assigned to the common area phone.</span></span> <span data-ttu-id="e1c60-116">Observe que você deve usar o formato E. 164 ao especificar o número de telefone.</span><span class="sxs-lookup"><span data-stu-id="e1c60-116">Note that you must use the E.164 format when specifying the phone number.</span></span>
    
      - <span data-ttu-id="e1c60-117">**RegistrarPool**: o nome de domínio totalmente qualificado (FQDN) do pool de registradores que hospedará o objeto Contact.</span><span class="sxs-lookup"><span data-stu-id="e1c60-117">**RegistrarPool**: The fully qualified domain name (FQDN) of the Registrar pool that will host the contact object.</span></span>
    
      - <span data-ttu-id="e1c60-118">**Ou**: nome distinto do contêiner do Active Directory onde o objeto de contato será criado.</span><span class="sxs-lookup"><span data-stu-id="e1c60-118">**OU**: Distinguished name of the Active Directory container where the contact object will be created.</span></span>
    
    <span data-ttu-id="e1c60-119">Recomendamos também que você forneça um nome de exibição dos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e1c60-119">We also recommend that you provide an Active Directory Domain Services display name.</span></span> <span data-ttu-id="e1c60-120">Caso contrário, será necessário usar um GUID para especificar a identidade do telefone.</span><span class="sxs-lookup"><span data-stu-id="e1c60-120">Otherwise, you will need to use a GUID to specify the phone Identity.</span></span> <span data-ttu-id="e1c60-121">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e1c60-121">For example:</span></span>
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a><span data-ttu-id="e1c60-122">Modificando um objeto de contato de telefone de área comum</span><span class="sxs-lookup"><span data-stu-id="e1c60-122">Modifying a common area phone contact object</span></span>

  - <span data-ttu-id="e1c60-123">Para modificar as propriedades de um telefone de área comum existente, objeto de contato use o cmdlet **set-CsCommonAreaPhone** .</span><span class="sxs-lookup"><span data-stu-id="e1c60-123">To modify the properties of an existing common area phone, contact object use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="e1c60-124">Por exemplo, este comando configura o endereço SIP para o telefone de área comum com o lobby DisplayName:</span><span class="sxs-lookup"><span data-stu-id="e1c60-124">For example, this command configures the SIP address for the common area phone with the DisplayName Lobby:</span></span>
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

<span data-ttu-id="e1c60-125">Para obter detalhes, consulte os tópicos de ajuda para o cmdlet [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) e o cmdlet [set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) .</span><span class="sxs-lookup"><span data-stu-id="e1c60-125">For details, see the Help topics for the [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) cmdlet and the [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

