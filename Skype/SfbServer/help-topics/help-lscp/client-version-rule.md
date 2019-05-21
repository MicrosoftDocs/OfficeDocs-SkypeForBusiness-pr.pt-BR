---
title: Regra de Versão do Cliente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
description: Uma política de versão de cliente é composta por um conjunto de regras de versão de cliente. Essas regras definem as ações que devem ser executadas quando os usuários tentam fazer logon com clientes específicos e versões do cliente.
ms.openlocfilehash: 6fa3ca3f59756c8a6fedb9fd8f1f457ca3f2df40
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277927"
---
# <a name="client-version-rule"></a><span data-ttu-id="4ad3b-104">Regra de Versão do Cliente</span><span class="sxs-lookup"><span data-stu-id="4ad3b-104">Client Version Rule</span></span>

<span data-ttu-id="4ad3b-p102">Uma política de versão de cliente é composta por um conjunto de regras de versão de cliente. Essas regras definem as ações que devem ser executadas quando os usuários tentam fazer logon com clientes específicos e versões do cliente.</span><span class="sxs-lookup"><span data-stu-id="4ad3b-p102">A client version policy is made up of a set of client version rules. These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="4ad3b-107">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="4ad3b-107">Tasks you can perform</span></span>

<span data-ttu-id="4ad3b-108">É possível executar as seguintes tarefas na página **Criar uma nova Configuração de Versão de Cliente** ou **Editar Configuração da Versão de Cliente**:</span><span class="sxs-lookup"><span data-stu-id="4ad3b-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="4ad3b-109">Adicionar novas regras a uma política de versão de cliente.</span><span class="sxs-lookup"><span data-stu-id="4ad3b-109">Add new rules to a client version policy.</span></span>

- <span data-ttu-id="4ad3b-110">Modificar as regras que compõem uma política de versão de cliente existente</span><span class="sxs-lookup"><span data-stu-id="4ad3b-110">Modify the rules that make up an existing client version policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="4ad3b-111">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="4ad3b-111">UI Reference</span></span>

<span data-ttu-id="4ad3b-112">As listas a seguir descrevem os menus, comando, campos e propriedades na página.</span><span class="sxs-lookup"><span data-stu-id="4ad3b-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="4ad3b-113">**Agente de usuário** Você pode selecionar um tipo de cliente na lista.</span><span class="sxs-lookup"><span data-stu-id="4ad3b-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="4ad3b-114">A tabela a seguir define códigos de agente de usuário.</span><span class="sxs-lookup"><span data-stu-id="4ad3b-114">The following table defines user agent codes.</span></span>

|<span data-ttu-id="4ad3b-115">**Nome do cliente**</span><span class="sxs-lookup"><span data-stu-id="4ad3b-115">**Client Name**</span></span>|<span data-ttu-id="4ad3b-116">**Agente de Usuário**</span><span class="sxs-lookup"><span data-stu-id="4ad3b-116">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4ad3b-117">Lync 2013, Lync 2010, Office Communicator</span><span class="sxs-lookup"><span data-stu-id="4ad3b-117">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="4ad3b-118">OC</span><span class="sxs-lookup"><span data-stu-id="4ad3b-118">OC</span></span>  <br/> |
|<span data-ttu-id="4ad3b-119">Lync Web App, Access Web Communicator</span><span class="sxs-lookup"><span data-stu-id="4ad3b-119">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="4ad3b-120">CWA</span><span class="sxs-lookup"><span data-stu-id="4ad3b-120">CWA</span></span>  <br/> |
|<span data-ttu-id="4ad3b-121">Lync Phone Edition, Office Communicator Phone</span><span class="sxs-lookup"><span data-stu-id="4ad3b-121">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="4ad3b-122">OCPhone</span><span class="sxs-lookup"><span data-stu-id="4ad3b-122">OCPhone</span></span>  <br/> |
|<span data-ttu-id="4ad3b-123">Communicator Phone Edition Platform</span><span class="sxs-lookup"><span data-stu-id="4ad3b-123">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="4ad3b-124">CPE</span><span class="sxs-lookup"><span data-stu-id="4ad3b-124">CPE</span></span>  <br/> |
|<span data-ttu-id="4ad3b-125">Unified Communications Platform</span><span class="sxs-lookup"><span data-stu-id="4ad3b-125">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="4ad3b-126">UCCP</span><span class="sxs-lookup"><span data-stu-id="4ad3b-126">UCCP</span></span>  <br/> |
|<span data-ttu-id="4ad3b-127">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="4ad3b-127">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="4ad3b-128">AOC</span><span class="sxs-lookup"><span data-stu-id="4ad3b-128">AOC</span></span>  <br/> |
|<span data-ttu-id="4ad3b-129">Live Meeting Add-In</span><span class="sxs-lookup"><span data-stu-id="4ad3b-129">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="4ad3b-130">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="4ad3b-130">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="4ad3b-131">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="4ad3b-131">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="4ad3b-132">LMC</span><span class="sxs-lookup"><span data-stu-id="4ad3b-132">LMC</span></span>  <br/> |
|<span data-ttu-id="4ad3b-133">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="4ad3b-133">Windows Messenger</span></span>  <br/> |<span data-ttu-id="4ad3b-134">WM</span><span class="sxs-lookup"><span data-stu-id="4ad3b-134">WM</span></span>  <br/> |
|<span data-ttu-id="4ad3b-135">Real-time Communications Client</span><span class="sxs-lookup"><span data-stu-id="4ad3b-135">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="4ad3b-136">RTC</span><span class="sxs-lookup"><span data-stu-id="4ad3b-136">RTC</span></span>  <br/> |
|<span data-ttu-id="4ad3b-137">Lync 2010 para iPad</span><span class="sxs-lookup"><span data-stu-id="4ad3b-137">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="4ad3b-138">iPadLync</span><span class="sxs-lookup"><span data-stu-id="4ad3b-138">iPadLync</span></span>  <br/> |
|<span data-ttu-id="4ad3b-139">Lync 2010 para iPhone</span><span class="sxs-lookup"><span data-stu-id="4ad3b-139">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="4ad3b-140">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="4ad3b-140">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="4ad3b-141">Lync 2010 para Windows Phone</span><span class="sxs-lookup"><span data-stu-id="4ad3b-141">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="4ad3b-142">WPLync</span><span class="sxs-lookup"><span data-stu-id="4ad3b-142">WPLync</span></span>  <br/> |
|<span data-ttu-id="4ad3b-143">Lync 2010 para Nokia</span><span class="sxs-lookup"><span data-stu-id="4ad3b-143">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="4ad3b-144">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="4ad3b-144">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="4ad3b-145">Lync 2010 para Android</span><span class="sxs-lookup"><span data-stu-id="4ad3b-145">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="4ad3b-146">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="4ad3b-146">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="4ad3b-147">Serviço de mobilidade</span><span class="sxs-lookup"><span data-stu-id="4ad3b-147">Mobility service</span></span>  <br/> |<span data-ttu-id="4ad3b-148">McxService</span><span class="sxs-lookup"><span data-stu-id="4ad3b-148">McxService</span></span>  <br/> |

- <span data-ttu-id="4ad3b-149">**Número da versão** Você pode especificar os números de versão para os campos a seguir ou usar caracteres curinga para indicar o número da versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="4ad3b-149">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>

  - <span data-ttu-id="4ad3b-150">**Versão principal** Especifica o número que corresponde à versão principal do cliente.</span><span class="sxs-lookup"><span data-stu-id="4ad3b-150">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>

  - <span data-ttu-id="4ad3b-151">**Versão secundária** Especifica o número que corresponde à versão secundária do cliente.</span><span class="sxs-lookup"><span data-stu-id="4ad3b-151">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>

  - <span data-ttu-id="4ad3b-152">**Criar** Especifica o número da compilação que corresponde à versão principal e secundária do cliente.</span><span class="sxs-lookup"><span data-stu-id="4ad3b-152">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>

  - <span data-ttu-id="4ad3b-153">**Atualização** do Especifica o número que corresponde à versão atualizada do cliente.</span><span class="sxs-lookup"><span data-stu-id="4ad3b-153">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>

- <span data-ttu-id="4ad3b-154">**Operação de comparação** Você pode especificar a operação correspondente para a versão do cliente que você especificou nas etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="4ad3b-154">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="4ad3b-155">As operações a seguir estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="4ad3b-155">The following operations are available:</span></span>

  - <span data-ttu-id="4ad3b-156">**Igual a**</span><span class="sxs-lookup"><span data-stu-id="4ad3b-156">**Same as**</span></span>

  - <span data-ttu-id="4ad3b-157">**Não é**</span><span class="sxs-lookup"><span data-stu-id="4ad3b-157">**Is not**</span></span>

  - <span data-ttu-id="4ad3b-158">**Mais novo que**</span><span class="sxs-lookup"><span data-stu-id="4ad3b-158">**Newer than**</span></span>

  - <span data-ttu-id="4ad3b-159">**Mais novo ou igual a**</span><span class="sxs-lookup"><span data-stu-id="4ad3b-159">**Newer than or same as**</span></span>

  - <span data-ttu-id="4ad3b-160">**Mais antigo que**</span><span class="sxs-lookup"><span data-stu-id="4ad3b-160">**Older than**</span></span>

  - <span data-ttu-id="4ad3b-161">**Mais antigo ou igual a**</span><span class="sxs-lookup"><span data-stu-id="4ad3b-161">**Older than or same as**</span></span>

- <span data-ttu-id="4ad3b-162">**Ação** Você pode especificar a ação a ser executada quando os critérios nas etapas anteriores forem atendidos.</span><span class="sxs-lookup"><span data-stu-id="4ad3b-162">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="4ad3b-163">As ações a seguir estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="4ad3b-163">The following actions are available:</span></span>

  - <span data-ttu-id="4ad3b-164">**Permite que** Permite que o cliente faça logon.</span><span class="sxs-lookup"><span data-stu-id="4ad3b-164">**Allow** Allows the client to log on.</span></span>

  - <span data-ttu-id="4ad3b-165">**Permitir e atualizar** Permite que o cliente faça logon e Receba atualizações do Windows Server Update Service ou do Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="4ad3b-165">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="4ad3b-166">Essa ação estará disponível somente quando o agente usuário **OC** for selecionado.</span><span class="sxs-lookup"><span data-stu-id="4ad3b-166">This action is available only when user agent **OC** is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4ad3b-167">Selecionar essa ação faz com que uma notificação seja exibida na próxima vez que os usuários entrarem no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="4ad3b-167">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="4ad3b-168">A notificação declara que uma atualização está disponível, mesmo se as atualizações ainda não tiverem sido lançadas pelo Windows Server Update Service ou Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="4ad3b-168">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="4ad3b-169">Para evitar confusão, você deve escolher esta ação apenas após as atualizações se tornarem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="4ad3b-169">To avoid confusion, you should choose this action only after updates become available.</span></span>

  - <span data-ttu-id="4ad3b-170">**Permitir com URL** Permite que o cliente faça logon e exiba uma mensagem sobre onde baixar outra versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="4ad3b-170">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="4ad3b-171">Especifique o URL no campo  **URL**.</span><span class="sxs-lookup"><span data-stu-id="4ad3b-171">You specify the URL in the **URL** field.</span></span>

  - <span data-ttu-id="4ad3b-172">**Bloquear** Impede que o cliente faça logon.</span><span class="sxs-lookup"><span data-stu-id="4ad3b-172">**Block** Prevents the client from logging on.</span></span>

  - <span data-ttu-id="4ad3b-173">**Bloquear e atualizar** Impede que o cliente faça logon e permite que o cliente Receba atualizações do Windows Server Update Service ou do Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="4ad3b-173">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="4ad3b-174">Essa ação estará disponível somente quando o agente usuário **OC** for selecionado.</span><span class="sxs-lookup"><span data-stu-id="4ad3b-174">This action is available only when user agent **OC** is selected.</span></span>

  - <span data-ttu-id="4ad3b-p110">**Bloquear com URL** Impede que o cliente faça logon e exibe uma mensagem sobre onde baixar outra versão do cliente. Especifique o URL no campo  **URL**.</span><span class="sxs-lookup"><span data-stu-id="4ad3b-p110">**Block with URL** prevents the client from logging on and displays a message about where to download another client version. You specify the URL in the **URL** field.</span></span>

<span data-ttu-id="4ad3b-p111">Para obter detalhes sobre a interoperabilidade entre clientes e versões de clientes, consulte [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) na documentação Planejamento. Para obter detalhes sobre como trabalhar com configurações de versão de cliente, consulte [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) na documentação Operações.</span><span class="sxs-lookup"><span data-stu-id="4ad3b-p111">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

