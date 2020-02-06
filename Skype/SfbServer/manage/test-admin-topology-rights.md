---
title: Testando direitos de topologia de administração no Skype for Business Server
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
description: Como testar os direitos de topologia no Skype for Business Server
ms.openlocfilehash: 1664a7e7d2b202b596a882e4b393cc15220806c9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817307"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a><span data-ttu-id="f50ee-103">Testando direitos de topologia de administração no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f50ee-103">Testing admin topology rights in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="f50ee-104">Cronograma de verificação</span><span class="sxs-lookup"><span data-stu-id="f50ee-104">Verification schedule</span></span>|<span data-ttu-id="f50ee-105">Após a implantação inicial do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f50ee-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="f50ee-106">Conforme necessário se surgirem problemas relacionados à permissão.</span><span class="sxs-lookup"><span data-stu-id="f50ee-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="f50ee-107">Ferramenta de teste</span><span class="sxs-lookup"><span data-stu-id="f50ee-107">Testing tool</span></span>|<span data-ttu-id="f50ee-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f50ee-108">Windows PowerShell</span></span>|
|<span data-ttu-id="f50ee-109">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="f50ee-109">Permissions required</span></span>|<span data-ttu-id="f50ee-110">Quando executado localmente usando o Shell de gerenciamento do Skype for Business Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f50ee-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br/><br/><span data-ttu-id="f50ee-111">Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Test-CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="f50ee-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="f50ee-112">Para ver uma lista de todas as funções RBAC que podem usar esse cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f50ee-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="f50ee-113">Get-CsAdminRole \| Where-Object {$ _. Cmdlets-corresponde a "Test-CsSetupPermission"}</span><span class="sxs-lookup"><span data-stu-id="f50ee-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsSetupPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="f50ee-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="f50ee-114">Description</span></span>

<span data-ttu-id="f50ee-115">Por padrão, somente os administradores de domínio podem habilitar uma topologia do Skype for Business Server e fazer grandes alterações na infraestrutura do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f50ee-115">By default, only domain administrators can enable a Skype for Business Server topology and make large changes to the Skype for Business Server infrastructure.</span></span> <span data-ttu-id="f50ee-116">Isso não será um problema, contanto que seus administradores de domínio e seus administradores do Skype for Business Server sejam os mesmos.</span><span class="sxs-lookup"><span data-stu-id="f50ee-116">This won't be a problem as long as your domain administrators and your Skype for Business Server administrators are one and the same.</span></span> <span data-ttu-id="f50ee-117">Em muitas organizações, os administradores do Skype for Business Server não mantêm direitos administrativos para todo o domínio.</span><span class="sxs-lookup"><span data-stu-id="f50ee-117">In many organizations, Skype for Business Server administrators do not hold administrative rights to the whole domain.</span></span> <span data-ttu-id="f50ee-118">Por padrão, isso significa que esses administradores (definidos como membros do grupo RTCUniversalServerAdmins) não podem fazer alterações de topologia do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f50ee-118">By default, that means that these administrators (defined as members of the RTCUniversalServerAdmins group) can't make Skype for Business Server topology changes.</span></span> <span data-ttu-id="f50ee-119">Para dar aos membros do grupo RTCUniversalServerAdmins o direito de fazer alterações de topologia, você deve atribuir as permissões necessárias do Active Directory usando o cmdlet [Grant-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission) .</span><span class="sxs-lookup"><span data-stu-id="f50ee-119">To give members of the RTCUniversalServerAdmins group the right to make topology changes, you must assign the required Active Directory permissions by using the [Grant-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission) cmdlet.</span></span>
 
<span data-ttu-id="f50ee-120">O cmdlet Test-CsSetupPermission verifica se as permissões necessárias necessárias para instalar o Skype for Business Server ou um de seus componentes estão configuradas no contêiner especificado do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f50ee-120">The Test-CsSetupPermission cmdlet verifies that the required permissions that are needed to install Skype for Business Server or one of its components are configured on the specified Active Directory container.</span></span> <span data-ttu-id="f50ee-121">Se as permissões não forem atribuídas, você poderá executar o cmdlet Grant-CsSetupPermission para dar aos membros do grupo RTCUniversalServerAdmins o direito de instalar e habilitar o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f50ee-121">If the permissions are not assigned, you can then run the Grant-CsSetupPermission cmdlet to give members of the RTCUniversalServerAdmins group the right to install and enable Skype for Business Server.</span></span>

## <a name="running-the-test"></a><span data-ttu-id="f50ee-122">Executar o teste</span><span class="sxs-lookup"><span data-stu-id="f50ee-122">Running the test</span></span>

<span data-ttu-id="f50ee-123">Para determinar se as permissões de configuração são atribuídas para um contêiner do Active Directory, chame o cmdlet Test-CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="f50ee-123">To determine whether setup permissions are assigned for an Active Directory container, call the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="f50ee-124">Especifique o nome diferenciado do contêiner a ser verificado.</span><span class="sxs-lookup"><span data-stu-id="f50ee-124">Specify the distinguished name of the container to be checked.</span></span> <span data-ttu-id="f50ee-125">Por exemplo, esse comando verifica as permissões de configuração no container ou = CsServers, DC = litwareinc, DC = com:</span><span class="sxs-lookup"><span data-stu-id="f50ee-125">For example, this command verifies setup permissions on the container ou=CsServers,dc=litwareinc,dc=com:</span></span>

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

<span data-ttu-id="f50ee-126">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) .</span><span class="sxs-lookup"><span data-stu-id="f50ee-126">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f50ee-127">Determinação do sucesso ou falha</span><span class="sxs-lookup"><span data-stu-id="f50ee-127">Determining success or failure</span></span>

<span data-ttu-id="f50ee-128">Se Test-CsSetupPermission determinar que as permissões necessárias já foram definidas em um contêiner do Active Directory, o cmdlet retornará o valor true:</span><span class="sxs-lookup"><span data-stu-id="f50ee-128">If Test-CsSetupPermission determines that the required permissions have already been set on an Active Directory container then the cmdlet will return the value True:</span></span>

<span data-ttu-id="f50ee-129">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="f50ee-129">True</span></span> 

<span data-ttu-id="f50ee-130">Se as permissões não estiverem definidas, Test-CsSetupPermission retornará o valor false.</span><span class="sxs-lookup"><span data-stu-id="f50ee-130">If permissions are not set, Test-CsSetupPermission will return the value False.</span></span> <span data-ttu-id="f50ee-131">Observe que esse valor normalmente será incluído em muitas mensagens de aviso.</span><span class="sxs-lookup"><span data-stu-id="f50ee-131">Note that this value will typically be enclosed in many warning messages.</span></span> <span data-ttu-id="f50ee-132">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f50ee-132">For example:</span></span>

<span data-ttu-id="f50ee-133">Aviso: entrada de controle de acesso (ACE) atl-cs-001\RTCUniversalServerAdmins; Habilitar ExtendedRight; Nenhuma Nenhuma 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span><span class="sxs-lookup"><span data-stu-id="f50ee-133">WARNING: Access control entry (ACE) atl-cs-001\RTCUniversalServerAdmins; Allow; ExtendedRight; None; None; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span></span> 

<span data-ttu-id="f50ee-134">Aviso: as entradas de controle de acesso (ACEs) no objeto "CN = Computers, DC = litwareinc, DC = com" não estão prontas.</span><span class="sxs-lookup"><span data-stu-id="f50ee-134">WARNING: The access control entries (ACEs) on the object "CN=Computers,DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="f50ee-135">Falso</span><span class="sxs-lookup"><span data-stu-id="f50ee-135">False</span></span> 

<span data-ttu-id="f50ee-136">Aviso: o processamento de "Test-CsSetupPermission" foi concluído com avisos.</span><span class="sxs-lookup"><span data-stu-id="f50ee-136">WARNING: "Test-CsSetupPermission" processing has completed with warnings.</span></span> <span data-ttu-id="f50ee-137">"2" avisos foram registrados durante a execução.</span><span class="sxs-lookup"><span data-stu-id="f50ee-137">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="f50ee-138">Aviso: os resultados detalhados podem ser encontrados em "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span><span class="sxs-lookup"><span data-stu-id="f50ee-138">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f50ee-139">Motivos pelos quais o teste pode ter falhado</span><span class="sxs-lookup"><span data-stu-id="f50ee-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="f50ee-140">Embora existam exceções raras, se Test-CsSetupPermission falhar, isso geralmente significa que as permissões de configuração não são atribuídas para o contêiner do Active Directory especificado.</span><span class="sxs-lookup"><span data-stu-id="f50ee-140">Although there are rare exceptions, if Test-CsSetupPermission fails that typically means that setup permissions are not assigned for the specified Active Directory container.</span></span> <span data-ttu-id="f50ee-141">Essas permissões podem ser atribuídas usando o cmdlet Grant-CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="f50ee-141">Those permissions can be assigned by using the Grant-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="f50ee-142">Por exemplo, esse comando concede permissões de configuração para o contêiner de computadores no domínio litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="f50ee-142">For example, this command grants setup permissions to the Computers container in the domain litwareinc.com:</span></span>

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

<span data-ttu-id="f50ee-143">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) .</span><span class="sxs-lookup"><span data-stu-id="f50ee-143">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>
