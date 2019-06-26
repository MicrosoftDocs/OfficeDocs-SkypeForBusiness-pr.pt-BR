---
title: Gerenciar contas de usuário usando o conector online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Use o cmdlet Get-CsOnlineUser no Windows PowerShell para obter informações sobre os usuários do Skype for Business online da sua organização.
ms.openlocfilehash: 02f3aa50f2256cd0d58f4c53cfa607c011bfa565
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221769"
---
# <a name="manage-user-accounts-using-the-online-connector"></a><span data-ttu-id="96224-103">Gerenciar contas de usuário usando o conector online</span><span class="sxs-lookup"><span data-stu-id="96224-103">Manage user accounts using the Online Connector</span></span>

## <a name="manage-user-accounts"></a><span data-ttu-id="96224-104">Gerenciar contas de usuário</span><span class="sxs-lookup"><span data-stu-id="96224-104">Manage user accounts</span></span>

<span data-ttu-id="96224-105">Este tópico inclui as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="96224-105">This topic contains the following sections:</span></span>

- [<span data-ttu-id="96224-106">Retornar informações sobre todos os seus usuários do Lync Online</span><span class="sxs-lookup"><span data-stu-id="96224-106">Return information about all your Skype for Business Online users</span></span>](manage-user-accounts-using-the-online-connector.md#BKAllUsers)

- [<span data-ttu-id="96224-107">Retornar informações para um usuário específico no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="96224-107">Return information for a specific user in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)

- [<span data-ttu-id="96224-108">Retornar informações específicas para usuários específicos no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="96224-108">Return specific information for specific users in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)

- [<span data-ttu-id="96224-109">Retornar uma lista filtrada de usuários no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="96224-109">Return a filtered list of users in Skype for Business Online</span></span>](manage-user-accounts-using-the-online-connector.md#BKListofUsers)

> [!NOTE]
> <span data-ttu-id="96224-110">O cmdlet **set-CsUser** também está incluído no conjunto de cmdlets disponíveis para os administradores do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="96224-110">The **Set-CsUser** cmdlet is also included in the set of cmdlets available to Skype for Business Online admins.</span></span> <span data-ttu-id="96224-111">No entanto, **set-CsUser** não pode ser usado no momento para gerenciar o Skype for Business Online, exceto para configurar o parâmetro _AudioVideoDisabled_ .</span><span class="sxs-lookup"><span data-stu-id="96224-111">However, **Set-CsUser** cannot currently be used to manage Skype for Business Online, except for setting the _AudioVideoDisabled_ parameter.</span></span> <span data-ttu-id="96224-112">Se você tentar executar o cmdlet com qualquer outro parâmetro, ele falhará com uma mensagem de erro semelhante a esta: não é possível definir "SipAddress".</span><span class="sxs-lookup"><span data-stu-id="96224-112">If you attempt to run the cmdlet with any other parameter, it will fail with an error message similar to this: Unable to set "SipAddress".</span></span> <span data-ttu-id="96224-113">Esse parâmetro é restrito dentro do PowerShell do locatário remoto.</span><span class="sxs-lookup"><span data-stu-id="96224-113">This parameter is restricted within Remote Tenant PowerShell.</span></span>

### <a name="return-information-about-all-your-skype-for-business-online-users"></a><span data-ttu-id="96224-114">Retornar informações sobre todos os seus usuários do Lync Online</span><span class="sxs-lookup"><span data-stu-id="96224-114">Return information about all your Skype for Business Online users</span></span>
<span data-ttu-id="96224-115"><a name="BKAllUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="96224-115"></span></span>

<span data-ttu-id="96224-116">Para retornar informações sobre todos os usuários que foram habilitados para o Skype for Business Online, chame o cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) sem parâmetros adicionais.</span><span class="sxs-lookup"><span data-stu-id="96224-116">To return information about all your users who have been enabled for Skype for Business Online, call the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet without any additional parameters.</span></span>

```
Get-CsOnlineUser
```

<span data-ttu-id="96224-117">Para retornar informações para um único usuário selecionado aleatoriamente (por exemplo, para usar esta conta para fins de teste), chame o cmdlet **Get-CsOnlineUser** e defina __ o parâmetro resulte como 1.</span><span class="sxs-lookup"><span data-stu-id="96224-117">To return information for a single, randomly selected user (for example, to use this account for test purposes), call the **Get-CsOnlineUser** cmdlet and set the _ResultSize_ parameter to 1.</span></span>

```
Get-CsOnlineUser -ResultSize 1
```

<span data-ttu-id="96224-118">Isso faz com que o cmdlet **Get-CsOnlineUser** retorne informações para apenas um usuário, independentemente de quantos usuários você tem em sua organização.</span><span class="sxs-lookup"><span data-stu-id="96224-118">That causes the **Get-CsOnlineUser** cmdlet to return information for just one user, regardless of how many users you have in your organization.</span></span> <span data-ttu-id="96224-119">Para retornar informações para cinco usuários, defina o valor do parâmetro _resulte_ como 5.</span><span class="sxs-lookup"><span data-stu-id="96224-119">To return information for five users, set the value of the _ResultSize_ parameter to 5.</span></span>

```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a><span data-ttu-id="96224-120">Retornar informações para um usuário específico no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="96224-120">Return information for a specific user in Skype for Business Online</span></span>
<span data-ttu-id="96224-121"><a name="BKSpecificUser"> </a></span><span class="sxs-lookup"><span data-stu-id="96224-121"></span></span>

<span data-ttu-id="96224-122">Há várias maneiras de fazer referência a uma conta de usuário específica ao chamar o cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) .</span><span class="sxs-lookup"><span data-stu-id="96224-122">There are multiple ways of referencing a specific user account when calling the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet.</span></span> <span data-ttu-id="96224-123">Você pode usar o nome de exibição dos serviços de domínio Active Directory (AD DS) do usuário.</span><span class="sxs-lookup"><span data-stu-id="96224-123">You can use the user's Active Directory Domain Services (AD DS) display name.</span></span>

```
Get-CsOnlineUser -Identity "Ken Myer"
```

<span data-ttu-id="96224-124">Você pode usar o endereço SIP do usuário.</span><span class="sxs-lookup"><span data-stu-id="96224-124">You can use the user's SIP address.</span></span>

```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

<span data-ttu-id="96224-125">Você pode usar o nome UPN do usuário.</span><span class="sxs-lookup"><span data-stu-id="96224-125">You can use the user's user principal name (UPN).</span></span>

```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a><span data-ttu-id="96224-126">Retornar informações específicas para usuários específicos no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="96224-126">Return specific information for specific users in Skype for Business Online</span></span>
<span data-ttu-id="96224-127"><a name="BKSpecificUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="96224-127"></span></span>

<span data-ttu-id="96224-128">Por padrão, o cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) retorna uma quantidade enorme de informações para cada conta de usuário do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="96224-128">By default, the [Get-CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) cmdlet returns a huge amount of information for each Skype for Business Online user account.</span></span> <span data-ttu-id="96224-129">Se você estiver interessado em apenas um subconjunto dessas informações, canalize os dados retornados para o cmdlet **Select-Object** .</span><span class="sxs-lookup"><span data-stu-id="96224-129">If you are interested in only a subset of that information, pipe the returned data to the **Select-Object** cmdlet.</span></span> <span data-ttu-id="96224-130">Por exemplo, esse comando retorna todos os dados do usuário Ken Myer e, em seguida, usa o cmdlet **Select-Object** para limitar as informações exibidas na tela para o nome para exibição do AD DS e o plano de discagem de Ken.</span><span class="sxs-lookup"><span data-stu-id="96224-130">For example, this command returns all the data for the user Ken Myer, and then uses the **Select-Object** cmdlet to limit the information displayed onscreen to Ken's AD DS display name and dial plan.</span></span>

```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="96224-131">O comando a seguir retorna o nome para exibição e o plano de discagem para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="96224-131">The following command returns the display name and dial plan for all your users.</span></span>

```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

<span data-ttu-id="96224-132">Para localizar as propriedades de uma conta de usuário do Skype for Business Online, use o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="96224-132">To find the properties of a Skype for Business Online user account, use the following command.</span></span>

```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a><span data-ttu-id="96224-133">Retornar uma lista filtrada de usuários no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="96224-133">Return a filtered list of users in Skype for Business Online</span></span>
<span data-ttu-id="96224-134"><a name="BKListofUsers"> </a></span><span class="sxs-lookup"><span data-stu-id="96224-134"></span></span>

<span data-ttu-id="96224-135">Ao usar o cmdlet [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) e os parâmetros _LdapFilter_ ou _Filter_ , você pode facilmente retornar informações sobre um conjunto direcionado de usuários.</span><span class="sxs-lookup"><span data-stu-id="96224-135">By using the [Get-CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) cmdlet and the _LdapFilter_ or _Filter_ parameters, you can easily return information about a targeted set of users.</span></span> <span data-ttu-id="96224-136">Por exemplo, esse comando retorna todos os usuários que trabalham no departamento financeiro.</span><span class="sxs-lookup"><span data-stu-id="96224-136">For example, this command returns all the users who work in the Finance department.</span></span>

```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a><span data-ttu-id="96224-137">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="96224-137">Related topics</span></span>
[<span data-ttu-id="96224-138">Configurar seu computador para o gerenciamento do Skype for Business online usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="96224-138">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)


