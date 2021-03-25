---
title: Testar permissões de administrador no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Como testar permissões de administrador no Skype for Business Server
ms.openlocfilehash: 535911c26bac5e3f1dadb2c8d59cffe82dc20c7a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122395"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a><span data-ttu-id="c0057-103">Testar permissões de administrador no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c0057-103">Testing admin permissions in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="c0057-104">Agendamento de verificação</span><span class="sxs-lookup"><span data-stu-id="c0057-104">Verification schedule</span></span>|<span data-ttu-id="c0057-105">Após a implantação inicial do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c0057-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="c0057-106">Conforme necessário se surgirem problemas relacionados à permissão.</span><span class="sxs-lookup"><span data-stu-id="c0057-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="c0057-107">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="c0057-107">Testing tool</span></span>|<span data-ttu-id="c0057-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c0057-108">Windows PowerShell</span></span>|
|<span data-ttu-id="c0057-109">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="c0057-109">Permissions required</span></span>|<span data-ttu-id="c0057-110">Quando executado localmente usando o Shell de Gerenciamento do Skype for Business Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="c0057-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br><br/><span data-ttu-id="c0057-111">Quando executado usando uma instância remota de Windows PowerShell, os usuários devem ter uma função RBAC com permissão para executar o cmdlet Test-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="c0057-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="c0057-112">Para ver uma lista de todas as funções do RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c0057-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="c0057-113">Get-CsAdminRole Where-Object \| {$_. Cmdlets -match "Test-CsOUPermission"}</span><span class="sxs-lookup"><span data-stu-id="c0057-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsOUPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="c0057-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="c0057-114">Description</span></span>

<span data-ttu-id="c0057-115">Quando você instala o Skype for Business Server, uma das tarefas executadas pelo programa de Instalação fornece ao grupo RTCUniversalUserAdmins as permissões do Active Directory necessárias para gerenciar usuários, computadores, contatos, contatos de aplicativos e pessoas InetOrg.</span><span class="sxs-lookup"><span data-stu-id="c0057-115">When you install Skype for Business Server, one of the tasks that was performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="c0057-116">Se você tiver desabilitado a herança de permissão no Active Directory, a instalação não poderá atribuir essas permissões.</span><span class="sxs-lookup"><span data-stu-id="c0057-116">If you have disabled permission inheritance in Active Directory, setup won't be able to assign those permissions.</span></span> <span data-ttu-id="c0057-117">Como resultado, os membros do grupo RTCUniversalUserAdmins não poderão gerenciar entidades do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c0057-117">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Skype for Business Server entities.</span></span> <span data-ttu-id="c0057-118">Esses privilégios de gerenciamento estarão disponíveis apenas para administradores de domínio.</span><span class="sxs-lookup"><span data-stu-id="c0057-118">Those management privileges will only be available to domain administrators.</span></span> 

<span data-ttu-id="c0057-119">O Test-CsOUPermission cmdlet verifica se as permissões necessárias para gerenciar usuários, computadores e outros objetos são definidas em um contêiner do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c0057-119">The Test-CsOUPermission cmdlet verifies that the required permissions needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="c0057-120">Se essas permissões não estão definidas, você pode resolver esse problema executando o [cmdlet Grant-CsOUPermission](/powershell/module/skype/Grant-CsOUPermission).</span><span class="sxs-lookup"><span data-stu-id="c0057-120">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission cmdlet](/powershell/module/skype/Grant-CsOUPermission).</span></span> 

<span data-ttu-id="c0057-121">Observe que Grant-CsOUPermission só pode atribuir permissões a membros do grupo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="c0057-121">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="c0057-122">Não é possível usar esse cmdlet para conceder permissões a um usuário ou grupo arbitrário.</span><span class="sxs-lookup"><span data-stu-id="c0057-122">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="c0057-123">Se você quiser que um usuário ou grupo diferente tenha permissões de gerenciamento de usuário, adicione esse usuário (ou grupo) ao grupo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="c0057-123">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span> 


## <a name="running-the-test"></a><span data-ttu-id="c0057-124">Executando o teste</span><span class="sxs-lookup"><span data-stu-id="c0057-124">Running the test</span></span>

<span data-ttu-id="c0057-125">Para verificar se as permissões de gerenciamento estão definidas em um contêiner, execute o cmdlet Test-CsOUPermission seguido pelo nome diferenciado do contêiner e pelo tipo de permissões que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="c0057-125">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="c0057-126">Por exemplo, este comando verifica se as permissões do usuário estão definidas em ou=Redmond,dc=litwareinc,dc=com:</span><span class="sxs-lookup"><span data-stu-id="c0057-126">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

<span data-ttu-id="c0057-127">Para verificar várias permissões usando um único comando, coloque cada tipo de permissão entre aspas e separe esses tipos usando vírgulas.</span><span class="sxs-lookup"><span data-stu-id="c0057-127">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="c0057-128">Por exemplo, este comando verifica permissões de usuário, computador e contato:</span><span class="sxs-lookup"><span data-stu-id="c0057-128">For example, this one command verifies user, computer, and contact permissions:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

<span data-ttu-id="c0057-129">Para obter mais informações, consulte [o tópico de ajuda para o cmdlet Test-CsOUPermission](/powershell/module/skype/test-csoupermission).</span><span class="sxs-lookup"><span data-stu-id="c0057-129">For more information, see the [help topic for the Test-CsOUPermission cmdlet](/powershell/module/skype/test-csoupermission).</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c0057-130">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="c0057-130">Determining success or failure</span></span>

<span data-ttu-id="c0057-131">Se as permissões necessárias já foram definidas, Test-CsOUPermission retornará uma resposta de uma palavra:</span><span class="sxs-lookup"><span data-stu-id="c0057-131">If the required permissions have already been set, Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="c0057-132">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="c0057-132">True</span></span>

<span data-ttu-id="c0057-133">Se as permissões necessárias não estão definidas, Test-CsOUPermission retornará o valor False.</span><span class="sxs-lookup"><span data-stu-id="c0057-133">If the required permissions are not set, Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="c0057-134">Talvez seja preciso pesquisar por um momento para encontrar esse valor.</span><span class="sxs-lookup"><span data-stu-id="c0057-134">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="c0057-135">Normalmente, ele será inserido dentro de vários avisos que acompanham.</span><span class="sxs-lookup"><span data-stu-id="c0057-135">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="c0057-136">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c0057-136">For example:</span></span>

<span data-ttu-id="c0057-137">AVISO: ace (entrada de controle de acesso) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendentes; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="c0057-137">WARNING: access control entry (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span> 

<span data-ttu-id="c0057-138">AVISO: As entradas de controle de acesso (ACEs) no objeto "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" não estão prontas.</span><span class="sxs-lookup"><span data-stu-id="c0057-138">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="c0057-139">Falso</span><span class="sxs-lookup"><span data-stu-id="c0057-139">False</span></span> 

<span data-ttu-id="c0057-140">AVISO: o processamento "Test-CsOUPermission" foi concluído com avisos.</span><span class="sxs-lookup"><span data-stu-id="c0057-140">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="c0057-141">Avisos "2" foram gravados durante essa executar.</span><span class="sxs-lookup"><span data-stu-id="c0057-141">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="c0057-142">AVISO: Os resultados detalhados podem ser encontrados em "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span><span class="sxs-lookup"><span data-stu-id="c0057-142">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c0057-143">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="c0057-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="c0057-144">Se Test-CsOUPermission falha, geralmente significa que a permissão especificada não foi atribuída ao grupo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="c0057-144">If Test-CsOUPermission fails, it usually means that the specified permission has not been assigned to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="c0057-145">Você pode resolver esse problema e atribuir as permissões necessárias usando o cmdlet Grant-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="c0057-145">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="c0057-146">Por exemplo, este comando fornece permissões de UO para usuários, contatos e inetOrgPersons para o grupo RTCUniversalUserAdmins:</span><span class="sxs-lookup"><span data-stu-id="c0057-146">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

<span data-ttu-id="c0057-147">Para obter mais informações, consulte [o tópico de ajuda para o cmdlet Test-CsOUPermission](/powershell/module/skype/test-csoupermission).</span><span class="sxs-lookup"><span data-stu-id="c0057-147">For more information, see the [help topic for the Test-CsOUPermission cmdlet](/powershell/module/skype/test-csoupermission).</span></span>