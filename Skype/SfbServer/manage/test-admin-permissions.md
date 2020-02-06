---
title: Testar permissões de administrador no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Como testar permissões de administrador no Skype for Business Server
ms.openlocfilehash: 97db574803b575d484240e7339d56603ae5432da
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817182"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a><span data-ttu-id="dbe3e-103">Testar permissões de administrador no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dbe3e-103">Testing admin permissions in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="dbe3e-104">Cronograma de verificação</span><span class="sxs-lookup"><span data-stu-id="dbe3e-104">Verification schedule</span></span>|<span data-ttu-id="dbe3e-105">Após a implantação inicial do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="dbe3e-106">Conforme necessário se surgirem problemas relacionados à permissão.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="dbe3e-107">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="dbe3e-107">Testing tool</span></span>|<span data-ttu-id="dbe3e-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dbe3e-108">Windows PowerShell</span></span>|
|<span data-ttu-id="dbe3e-109">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="dbe3e-109">Permissions required</span></span>|<span data-ttu-id="dbe3e-110">Quando executado localmente usando o Shell de gerenciamento do Skype for Business Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br><br/><span data-ttu-id="dbe3e-111">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="dbe3e-112">Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="dbe3e-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="dbe3e-113">Get-CsAdminRole \| Where-Object {$ _. Cmdlets-corresponde a "Test-CsOUPermission"}</span><span class="sxs-lookup"><span data-stu-id="dbe3e-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsOUPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="dbe3e-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="dbe3e-114">Description</span></span>

<span data-ttu-id="dbe3e-115">Ao instalar o Skype for Business Server, uma das tarefas realizadas pelo programa de instalação fornece ao grupo RTCUniversalUserAdmins as permissões do Active Directory necessárias para gerenciar usuários, computadores, contatos, contatos de aplicativos e InetOrg pessoas.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-115">When you install Skype for Business Server, one of the tasks that was performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="dbe3e-116">Se você desabilitou a herança de permissão no Active Directory, a configuração não poderá atribuir essas permissões.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-116">If you have disabled permission inheritance in Active Directory, setup won't be able to assign those permissions.</span></span> <span data-ttu-id="dbe3e-117">Como resultado, os membros do grupo RTCUniversalUserAdmins não poderão gerenciar entidades do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-117">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Skype for Business Server entities.</span></span> <span data-ttu-id="dbe3e-118">Esses privilégios de gerenciamento só estarão disponíveis para administradores de domínio.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-118">Those management privileges will only be available to domain administrators.</span></span> 

<span data-ttu-id="dbe3e-119">O cmdlet Test-CsOUPermission verifica se as permissões necessárias necessárias para gerenciar usuários, computadores e outros objetos estão definidas em um contêiner do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-119">The Test-CsOUPermission cmdlet verifies that the required permissions needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="dbe3e-120">Se essas permissões não estiverem definidas, você poderá resolver esse problema executando o [cmdlet Grant-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission).</span><span class="sxs-lookup"><span data-stu-id="dbe3e-120">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission).</span></span> 

<span data-ttu-id="dbe3e-121">Observe que Grant-CsOUPermission só pode atribuir permissões a membros do grupo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-121">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="dbe3e-122">Você não pode usar esse cmdlet para conceder permissões a um usuário ou grupo arbitrário.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-122">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="dbe3e-123">Se quiser que um usuário ou grupo diferente tenha permissões de gerenciamento de usuário, você deve adicionar esse usuário (ou grupo) ao grupo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-123">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span> 


## <a name="running-the-test"></a><span data-ttu-id="dbe3e-124">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="dbe3e-124">Running the test</span></span>

<span data-ttu-id="dbe3e-125">Para verificar se as permissões de gerenciamento estão definidas em um contêiner, execute o cmdlet Test-CsOUPermission seguido pelo nome distinto do contêiner e pelo tipo de permissões que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-125">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="dbe3e-126">Por exemplo, esse comando verifica se as permissões de usuário estão definidas na UO ou em Redmond, DC = litwareinc, DC = com:</span><span class="sxs-lookup"><span data-stu-id="dbe3e-126">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

<span data-ttu-id="dbe3e-127">Para verificar várias permissões usando um único comando, coloque cada tipo de permissão entre aspas e, em seguida, separe esses tipos usando vírgulas.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-127">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="dbe3e-128">Por exemplo, este comando verifica as permissões de usuário, computador e contato:</span><span class="sxs-lookup"><span data-stu-id="dbe3e-128">For example, this one command verifies user, computer, and contact permissions:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

<span data-ttu-id="dbe3e-129">Para obter mais informações, consulte o [tópico da ajuda para o cmdlet Test-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).</span><span class="sxs-lookup"><span data-stu-id="dbe3e-129">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="dbe3e-130">Determinação do sucesso ou falha</span><span class="sxs-lookup"><span data-stu-id="dbe3e-130">Determining success or failure</span></span>

<span data-ttu-id="dbe3e-131">Se as permissões necessárias já foram definidas, Test-CsOUPermission retornará uma resposta de uma palavra:</span><span class="sxs-lookup"><span data-stu-id="dbe3e-131">If the required permissions have already been set, Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="dbe3e-132">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="dbe3e-132">True</span></span>

<span data-ttu-id="dbe3e-133">Se as permissões necessárias não estiverem definidas, Test-CsOUPermission retornará o valor false.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-133">If the required permissions are not set, Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="dbe3e-134">Talvez seja necessário procurar por um momento para encontrar esse valor.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-134">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="dbe3e-135">Geralmente, ele será inserido dentro de vários avisos que acompanham.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-135">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="dbe3e-136">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="dbe3e-136">For example:</span></span>

<span data-ttu-id="dbe3e-137">Aviso: entrada de controle de acesso (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; habilitar ReadProperty; ContainerInherit; Descendentes; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="dbe3e-137">WARNING: access control entry (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span> 

<span data-ttu-id="dbe3e-138">Aviso: as entradas de controle de acesso (ACEs) no objeto "UO = América do Access = atl-cs-001\DC = litwareinc, DC = com" não estão prontas.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-138">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="dbe3e-139">Falso</span><span class="sxs-lookup"><span data-stu-id="dbe3e-139">False</span></span> 

<span data-ttu-id="dbe3e-140">Aviso: o processamento de "Test-CsOUPermission" foi concluído com avisos.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-140">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="dbe3e-141">"2" avisos foram registrados durante a execução.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-141">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="dbe3e-142">Aviso: os resultados detalhados podem ser encontrados em "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span><span class="sxs-lookup"><span data-stu-id="dbe3e-142">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="dbe3e-143">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="dbe3e-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="dbe3e-144">Se Test-CsOUPermission falhar, geralmente significa que a permissão especificada não foi atribuída ao grupo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-144">If Test-CsOUPermission fails, it usually means that the specified permission has not been assigned to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="dbe3e-145">Você pode resolver esse problema e atribuir as permissões necessárias, usando o cmdlet Grant-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-145">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="dbe3e-146">Por exemplo, esse comando fornece permissões de OU para usuários, contatos e inetOrgPersons ao grupo RTCUniversalUserAdmins:</span><span class="sxs-lookup"><span data-stu-id="dbe3e-146">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

<span data-ttu-id="dbe3e-147">Para obter mais informações, consulte o [tópico da ajuda para o cmdlet Test-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).</span><span class="sxs-lookup"><span data-stu-id="dbe3e-147">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).</span></span>
