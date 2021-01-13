---
title: Testando direitos de topologia de administrador no Skype for Business Server
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
description: Como testar direitos de topologia no Skype for Business Server
ms.openlocfilehash: a6bbebd44387911fdb69679a16ab052c673f0b10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832841"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a><span data-ttu-id="d55c9-103">Testando direitos de topologia de administrador no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d55c9-103">Testing admin topology rights in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="d55c9-104">Agenda de verificação</span><span class="sxs-lookup"><span data-stu-id="d55c9-104">Verification schedule</span></span>|<span data-ttu-id="d55c9-105">Após a implantação inicial do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d55c9-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="d55c9-106">Conforme necessário, se surgirem problemas relacionados à permissão.</span><span class="sxs-lookup"><span data-stu-id="d55c9-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="d55c9-107">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="d55c9-107">Testing tool</span></span>|<span data-ttu-id="d55c9-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d55c9-108">Windows PowerShell</span></span>|
|<span data-ttu-id="d55c9-109">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="d55c9-109">Permissions required</span></span>|<span data-ttu-id="d55c9-110">Quando executados localmente usando o Shell de Gerenciamento do Skype for Business Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d55c9-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br/><br/><span data-ttu-id="d55c9-111">Ao executar usando uma instância remota do Windows PowerShell, os usuários devem ter uma função RBAC com permissão para executar o Test-CsSetupPermission cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d55c9-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="d55c9-112">Para ver uma lista de todas as funções do RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d55c9-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="d55c9-113">Get-CsAdminRole Where-Object \| {$_. Cmdlets -match "Test-CsSetupPermission"}</span><span class="sxs-lookup"><span data-stu-id="d55c9-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsSetupPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="d55c9-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="d55c9-114">Description</span></span>

<span data-ttu-id="d55c9-115">Por padrão, somente administradores de domínio podem habilitar uma topologia do Skype for Business Server e fazer grandes alterações na infraestrutura do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d55c9-115">By default, only domain administrators can enable a Skype for Business Server topology and make large changes to the Skype for Business Server infrastructure.</span></span> <span data-ttu-id="d55c9-116">Isso não será um problema, desde que seus administradores de domínio e seus administradores do Skype for Business Server sejam os mesmos.</span><span class="sxs-lookup"><span data-stu-id="d55c9-116">This won't be a problem as long as your domain administrators and your Skype for Business Server administrators are one and the same.</span></span> <span data-ttu-id="d55c9-117">Em muitas organizações, os administradores do Skype for Business Server não têm direitos administrativos para todo o domínio.</span><span class="sxs-lookup"><span data-stu-id="d55c9-117">In many organizations, Skype for Business Server administrators do not hold administrative rights to the whole domain.</span></span> <span data-ttu-id="d55c9-118">Por padrão, isso significa que esses administradores (definidos como membros do grupo RTCUniversalServerAdmins) não podem fazer alterações na topologia do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d55c9-118">By default, that means that these administrators (defined as members of the RTCUniversalServerAdmins group) can't make Skype for Business Server topology changes.</span></span> <span data-ttu-id="d55c9-119">Para conceder aos membros do grupo RTCUniversalServerAdmins o direito de fazer alterações na topologia, você deve atribuir as permissões necessárias do Active Directory usando o cmdlet [Grant-CsSetupPermission.](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)</span><span class="sxs-lookup"><span data-stu-id="d55c9-119">To give members of the RTCUniversalServerAdmins group the right to make topology changes, you must assign the required Active Directory permissions by using the [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) cmdlet.</span></span>
 
<span data-ttu-id="d55c9-120">O Test-CsSetupPermission cmdlet verifica se as permissões necessárias para instalar o Skype for Business Server ou um de seus componentes estão configuradas no contêiner do Active Directory especificado.</span><span class="sxs-lookup"><span data-stu-id="d55c9-120">The Test-CsSetupPermission cmdlet verifies that the required permissions that are needed to install Skype for Business Server or one of its components are configured on the specified Active Directory container.</span></span> <span data-ttu-id="d55c9-121">Se as permissões não são atribuídas, você pode executar o cmdlet Grant-CsSetupPermission para dar aos membros do grupo RTCUniversalServerAdmins o direito de instalar e habilitar o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d55c9-121">If the permissions are not assigned, you can then run the Grant-CsSetupPermission cmdlet to give members of the RTCUniversalServerAdmins group the right to install and enable Skype for Business Server.</span></span>

## <a name="running-the-test"></a><span data-ttu-id="d55c9-122">Executando o teste</span><span class="sxs-lookup"><span data-stu-id="d55c9-122">Running the test</span></span>

<span data-ttu-id="d55c9-123">Para determinar se as permissões de instalação são atribuídas a um contêiner do Active Directory, chame o Test-CsSetupPermission cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d55c9-123">To determine whether setup permissions are assigned for an Active Directory container, call the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="d55c9-124">Especifique o nome diferenciado do contêiner a ser verificado.</span><span class="sxs-lookup"><span data-stu-id="d55c9-124">Specify the distinguished name of the container to be checked.</span></span> <span data-ttu-id="d55c9-125">Por exemplo, este comando verifica as permissões de instalação no contêiner ou=CsServers,dc=litwareinc,dc=com:</span><span class="sxs-lookup"><span data-stu-id="d55c9-125">For example, this command verifies setup permissions on the container ou=CsServers,dc=litwareinc,dc=com:</span></span>

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

<span data-ttu-id="d55c9-126">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Test-CsSetupPermission.](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission)</span><span class="sxs-lookup"><span data-stu-id="d55c9-126">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="d55c9-127">Determinando o sucesso ou a falha</span><span class="sxs-lookup"><span data-stu-id="d55c9-127">Determining success or failure</span></span>

<span data-ttu-id="d55c9-128">Se Test-CsSetupPermission determinar que as permissões necessárias já foram definidas em um contêiner do Active Directory, o cmdlet retornará o valor True:</span><span class="sxs-lookup"><span data-stu-id="d55c9-128">If Test-CsSetupPermission determines that the required permissions have already been set on an Active Directory container then the cmdlet will return the value True:</span></span>

<span data-ttu-id="d55c9-129">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="d55c9-129">True</span></span> 

<span data-ttu-id="d55c9-130">Se as permissões não estão definidas, Test-CsSetupPermission retornará o valor False.</span><span class="sxs-lookup"><span data-stu-id="d55c9-130">If permissions are not set, Test-CsSetupPermission will return the value False.</span></span> <span data-ttu-id="d55c9-131">Observe que esse valor normalmente será incluído em muitas mensagens de aviso.</span><span class="sxs-lookup"><span data-stu-id="d55c9-131">Note that this value will typically be enclosed in many warning messages.</span></span> <span data-ttu-id="d55c9-132">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d55c9-132">For example:</span></span>

<span data-ttu-id="d55c9-133">AVISO: Entrada de controle de acesso (ACE) atl-cs-001\RTCUniversalServerAdmins; Permitir; ExtendedRight; Nenhum; Nenhum; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span><span class="sxs-lookup"><span data-stu-id="d55c9-133">WARNING: Access control entry (ACE) atl-cs-001\RTCUniversalServerAdmins; Allow; ExtendedRight; None; None; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span></span> 

<span data-ttu-id="d55c9-134">AVISO: as ACEs (entradas de controle de acesso) no objeto "CN=Computers,DC=litwareinc,DC=com" não estão prontas.</span><span class="sxs-lookup"><span data-stu-id="d55c9-134">WARNING: The access control entries (ACEs) on the object "CN=Computers,DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="d55c9-135">Falso</span><span class="sxs-lookup"><span data-stu-id="d55c9-135">False</span></span> 

<span data-ttu-id="d55c9-136">AVISO: o processamento "Test-CsSetupPermission" foi concluído com avisos.</span><span class="sxs-lookup"><span data-stu-id="d55c9-136">WARNING: "Test-CsSetupPermission" processing has completed with warnings.</span></span> <span data-ttu-id="d55c9-137">Os avisos "2" foram gravados durante essa operação.</span><span class="sxs-lookup"><span data-stu-id="d55c9-137">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="d55c9-138">AVISO: Resultados detalhados podem ser encontrados em "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span><span class="sxs-lookup"><span data-stu-id="d55c9-138">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="d55c9-139">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="d55c9-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="d55c9-140">Embora existam raras exceções, se Test-CsSetupPermission falhar, isso geralmente significa que as permissões de configuração não são atribuídas para o contêiner do Active Directory especificado.</span><span class="sxs-lookup"><span data-stu-id="d55c9-140">Although there are rare exceptions, if Test-CsSetupPermission fails that typically means that setup permissions are not assigned for the specified Active Directory container.</span></span> <span data-ttu-id="d55c9-141">Essas permissões podem ser atribuídas usando o Grant-CsSetupPermission cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d55c9-141">Those permissions can be assigned by using the Grant-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="d55c9-142">Por exemplo, este comando concede permissões de configuração para o contêiner Computadores no domínio litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="d55c9-142">For example, this command grants setup permissions to the Computers container in the domain litwareinc.com:</span></span>

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

<span data-ttu-id="d55c9-143">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Test-CsSetupPermission.](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission)</span><span class="sxs-lookup"><span data-stu-id="d55c9-143">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>
