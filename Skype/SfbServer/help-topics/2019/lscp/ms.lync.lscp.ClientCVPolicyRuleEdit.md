---
title: Regra de Versão do Cliente
ms.author: dianef
author: dianef77
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
ROBOTS: NOINDEX, NOFOLLOW
description: Uma política de versão de cliente é composta por um conjunto de regras de versão de cliente. Essas regras definem as ações que devem ser executadas quando os usuários tentam fazer logon com clientes específicos e versões do cliente.
ms.openlocfilehash: affd6ddaf6fe1f8a41d8d8bd5d74e709ddb5e31e
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23255120"
---
# <a name="client-version-rule"></a><span data-ttu-id="0f740-104">Regra de Versão do Cliente</span><span class="sxs-lookup"><span data-stu-id="0f740-104">Client Version Rule</span></span>

<span data-ttu-id="0f740-p102">Uma política de versão de cliente é composta por um conjunto de regras de versão de cliente. Essas regras definem as ações que devem ser executadas quando os usuários tentam fazer logon com clientes específicos e versões do cliente.</span><span class="sxs-lookup"><span data-stu-id="0f740-p102">A client version policy is made up of a set of client version rules. These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="0f740-107">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="0f740-107">Tasks you can perform</span></span>

<span data-ttu-id="0f740-108">É possível executar as seguintes tarefas na página **Criar uma nova Configuração de Versão de Cliente** ou **Editar Configuração da Versão de Cliente**:</span><span class="sxs-lookup"><span data-stu-id="0f740-108">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="0f740-109">Adicionar novas regras a uma política de versão de cliente.</span><span class="sxs-lookup"><span data-stu-id="0f740-109">Add new rules to a client version policy.</span></span>

- <span data-ttu-id="0f740-110">Modificar as regras que compõem uma política de versão de cliente existente</span><span class="sxs-lookup"><span data-stu-id="0f740-110">Modify the rules that make up an existing client version policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="0f740-111">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="0f740-111">UI Reference</span></span>

<span data-ttu-id="0f740-112">As listas a seguir descrevem os menus, comando, campos e propriedades na página.</span><span class="sxs-lookup"><span data-stu-id="0f740-112">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="0f740-113">**Agente do usuário** Você pode selecionar um tipo de cliente da lista.</span><span class="sxs-lookup"><span data-stu-id="0f740-113">**User agent** You can select a client type from the list.</span></span> <span data-ttu-id="0f740-114">A tabela a seguir define códigos de agente de usuário.</span><span class="sxs-lookup"><span data-stu-id="0f740-114">The following table defines user agent codes.</span></span> <span data-ttu-id="0f740-115">Esta lista inclui os tipos de cliente herdado, algumas das quais não são mais suportadas.</span><span class="sxs-lookup"><span data-stu-id="0f740-115">This list includes legacy client types, some of which are no longer supported.</span></span>

|<span data-ttu-id="0f740-116">**Nome do cliente**</span><span class="sxs-lookup"><span data-stu-id="0f740-116">**Client Name**</span></span>|<span data-ttu-id="0f740-117">**Agente do usuário**</span><span class="sxs-lookup"><span data-stu-id="0f740-117">**User Agent**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0f740-118">Lync 2013, Lync 2010, o Office Communicator</span><span class="sxs-lookup"><span data-stu-id="0f740-118">Lync 2013, Lync 2010, Office Communicator</span></span>  <br/> |<span data-ttu-id="0f740-119">OC</span><span class="sxs-lookup"><span data-stu-id="0f740-119">OC</span></span>  <br/> |
|<span data-ttu-id="0f740-120">Lync Web App, o Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="0f740-120">Lync Web App, Communicator Web Access</span></span>  <br/> |<span data-ttu-id="0f740-121">CWA</span><span class="sxs-lookup"><span data-stu-id="0f740-121">CWA</span></span>  <br/> |
|<span data-ttu-id="0f740-122">O Lync Phone Edition, o Office Communicator Phone</span><span class="sxs-lookup"><span data-stu-id="0f740-122">Lync Phone Edition, Office Communicator Phone</span></span>  <br/> |<span data-ttu-id="0f740-123">OCPhone</span><span class="sxs-lookup"><span data-stu-id="0f740-123">OCPhone</span></span>  <br/> |
|<span data-ttu-id="0f740-124">Communicator Phone Edition Platform</span><span class="sxs-lookup"><span data-stu-id="0f740-124">Communicator Phone Edition Platform</span></span>  <br/> |<span data-ttu-id="0f740-125">CPE</span><span class="sxs-lookup"><span data-stu-id="0f740-125">CPE</span></span>  <br/> |
|<span data-ttu-id="0f740-126">Unified Communications Platform</span><span class="sxs-lookup"><span data-stu-id="0f740-126">Unified Communications Platform</span></span>  <br/> |<span data-ttu-id="0f740-127">UCCP</span><span class="sxs-lookup"><span data-stu-id="0f740-127">UCCP</span></span>  <br/> |
|<span data-ttu-id="0f740-128">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="0f740-128">Lync 2010 Attendee</span></span>  <br/> |<span data-ttu-id="0f740-129">AOC</span><span class="sxs-lookup"><span data-stu-id="0f740-129">AOC</span></span>  <br/> |
|<span data-ttu-id="0f740-130">Live Meeting Add-In</span><span class="sxs-lookup"><span data-stu-id="0f740-130">Live Meeting Add-In</span></span>  <br/> |<span data-ttu-id="0f740-131">LiveMeetingAddins</span><span class="sxs-lookup"><span data-stu-id="0f740-131">LiveMeetingAddins</span></span>  <br/> |
|<span data-ttu-id="0f740-132">Office Live Meeting</span><span class="sxs-lookup"><span data-stu-id="0f740-132">Office Live Meeting</span></span>  <br/> |<span data-ttu-id="0f740-133">LMC</span><span class="sxs-lookup"><span data-stu-id="0f740-133">LMC</span></span>  <br/> |
|<span data-ttu-id="0f740-134">Windows Messenger</span><span class="sxs-lookup"><span data-stu-id="0f740-134">Windows Messenger</span></span>  <br/> |<span data-ttu-id="0f740-135">WM</span><span class="sxs-lookup"><span data-stu-id="0f740-135">WM</span></span>  <br/> |
|<span data-ttu-id="0f740-136">Real-time Communications Client</span><span class="sxs-lookup"><span data-stu-id="0f740-136">Real-time Communications Client</span></span>  <br/> |<span data-ttu-id="0f740-137">RTC</span><span class="sxs-lookup"><span data-stu-id="0f740-137">RTC</span></span>  <br/> |
|<span data-ttu-id="0f740-138">Lync 2010 para iPad</span><span class="sxs-lookup"><span data-stu-id="0f740-138">Lync 2010 for iPad</span></span>  <br/> |<span data-ttu-id="0f740-139">iPadLync</span><span class="sxs-lookup"><span data-stu-id="0f740-139">iPadLync</span></span>  <br/> |
|<span data-ttu-id="0f740-140">Lync 2010 para iPhone</span><span class="sxs-lookup"><span data-stu-id="0f740-140">Lync 2010 for iPhone</span></span>  <br/> |<span data-ttu-id="0f740-141">iPhoneLync</span><span class="sxs-lookup"><span data-stu-id="0f740-141">iPhoneLync</span></span>  <br/> |
|<span data-ttu-id="0f740-142">Lync 2010 para Windows Phone</span><span class="sxs-lookup"><span data-stu-id="0f740-142">Lync 2010 for Windows Phone</span></span>  <br/> |<span data-ttu-id="0f740-143">WPLync</span><span class="sxs-lookup"><span data-stu-id="0f740-143">WPLync</span></span>  <br/> |
|<span data-ttu-id="0f740-144">Lync 2010 para Nokia</span><span class="sxs-lookup"><span data-stu-id="0f740-144">Lync 2010 for Nokia</span></span>  <br/> |<span data-ttu-id="0f740-145">NokiaLync</span><span class="sxs-lookup"><span data-stu-id="0f740-145">NokiaLync</span></span>  <br/> |
|<span data-ttu-id="0f740-146">Lync 2010 para Android</span><span class="sxs-lookup"><span data-stu-id="0f740-146">Lync 2010 for Android</span></span>  <br/> |<span data-ttu-id="0f740-147">AndroidLync</span><span class="sxs-lookup"><span data-stu-id="0f740-147">AndroidLync</span></span>  <br/> |
|<span data-ttu-id="0f740-148">Serviço de mobilidade</span><span class="sxs-lookup"><span data-stu-id="0f740-148">Mobility service</span></span>  <br/> |<span data-ttu-id="0f740-149">McxService</span><span class="sxs-lookup"><span data-stu-id="0f740-149">McxService</span></span>  <br/> |

- <span data-ttu-id="0f740-150">**Número de versão** Você pode especificar os números de versão para os seguintes campos ou usar caracteres curinga para indicar o número de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="0f740-150">**Version number** You can specify the version numbers for the following fields, or use wildcards to indicate the client version number.</span></span>

  - <span data-ttu-id="0f740-151">**Versão principal** Especifica o número que corresponde à principal versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="0f740-151">**Major version** Specifies the number that corresponds to the major release of the client.</span></span>

  - <span data-ttu-id="0f740-152">**Versão secundária** Especifica o número que corresponde à versão secundária do cliente.</span><span class="sxs-lookup"><span data-stu-id="0f740-152">**Minor version** Specifies the number that corresponds to the minor release of the client.</span></span>

  - <span data-ttu-id="0f740-153">**Construir** Especifica o número de compilação que corresponde à versão principal e secundária do cliente.</span><span class="sxs-lookup"><span data-stu-id="0f740-153">**Build** Specifies the build number that corresponds to the major and minor release of the client.</span></span>

  - <span data-ttu-id="0f740-154">**Atualização** Especifica o número que corresponde à versão atualizada do cliente.</span><span class="sxs-lookup"><span data-stu-id="0f740-154">**Update** Specifies the number that corresponds to the updated release of the client.</span></span>

- <span data-ttu-id="0f740-155">**Operação de comparação** Você pode especificar a operação correspondente para a versão de cliente especificada nas etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="0f740-155">**Comparison operation** You can specify the matching operation for the client version you specified in the preceding steps.</span></span> <span data-ttu-id="0f740-156">As operações a seguir estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="0f740-156">The following operations are available:</span></span>

  - <span data-ttu-id="0f740-157">**Igual a**</span><span class="sxs-lookup"><span data-stu-id="0f740-157">**Same as**</span></span>

  - <span data-ttu-id="0f740-158">**Não é**</span><span class="sxs-lookup"><span data-stu-id="0f740-158">**Is not**</span></span>

  - <span data-ttu-id="0f740-159">**Mais novo que**</span><span class="sxs-lookup"><span data-stu-id="0f740-159">**Newer than**</span></span>

  - <span data-ttu-id="0f740-160">**Mais novo ou igual a**</span><span class="sxs-lookup"><span data-stu-id="0f740-160">**Newer than or same as**</span></span>

  - <span data-ttu-id="0f740-161">**Mais antigo que**</span><span class="sxs-lookup"><span data-stu-id="0f740-161">**Older than**</span></span>

  - <span data-ttu-id="0f740-162">**Mais antigo ou igual a**</span><span class="sxs-lookup"><span data-stu-id="0f740-162">**Older than or same as**</span></span>

- <span data-ttu-id="0f740-163">**Ação** Você pode especificar a ação a ser executada quando os critérios nas etapas anteriores forem atendidos.</span><span class="sxs-lookup"><span data-stu-id="0f740-163">**Action** You can specify the action to perform when the criteria in the preceding steps are met.</span></span> <span data-ttu-id="0f740-164">As ações a seguir estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="0f740-164">The following actions are available:</span></span>

  - <span data-ttu-id="0f740-165">**Permitir** Permite que o cliente faça logon.</span><span class="sxs-lookup"><span data-stu-id="0f740-165">**Allow** Allows the client to log on.</span></span>

  - <span data-ttu-id="0f740-166">**Permitir e atualizar** Permite que o cliente faça logon e receber atualizações de serviço de atualização do Windows Server ou o Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="0f740-166">**Allow and Upgrade** Allows the client to log on and receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="0f740-167">Essa ação estará disponível somente quando o agente usuário **OC** for selecionado.</span><span class="sxs-lookup"><span data-stu-id="0f740-167">This action is available only when user agent **OC** is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0f740-168">Selecionar esta ação faz com que uma notificação apareça os próxima vez que os usuários entram no Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="0f740-168">Selecting this action causes a notification to appear the next time users sign in to Skype for Business.</span></span> <span data-ttu-id="0f740-169">A notificação declara que uma atualização está disponível, mesmo se as atualizações ainda não tiverem sido lançadas pelo Windows Server Update Service ou Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="0f740-169">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="0f740-170">Para evitar confusão, você deve escolher esta ação apenas após as atualizações se tornarem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="0f740-170">To avoid confusion, you should choose this action only after updates become available.</span></span>

  - <span data-ttu-id="0f740-171">**Permitir com URL** Permite que o cliente faça logon e exibe uma mensagem sobre onde baixar outra versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="0f740-171">**Allow with URL** Allows the client to log on and displays a message about where to download another client version.</span></span> <span data-ttu-id="0f740-172">Especifique o URL no campo  **URL**.</span><span class="sxs-lookup"><span data-stu-id="0f740-172">You specify the URL in the **URL** field.</span></span>

  - <span data-ttu-id="0f740-173">**Bloquear** Impede o cliente de logon.</span><span class="sxs-lookup"><span data-stu-id="0f740-173">**Block** Prevents the client from logging on.</span></span>

  - <span data-ttu-id="0f740-174">**Bloquear e atualização** Impede que o cliente logon e permite que o cliente recebe atualizações do serviço de atualização do Windows Server ou Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="0f740-174">**Block and Upgrade** Prevents the client from logging on and allows the client to receive updates from Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="0f740-175">Essa ação estará disponível somente quando o agente usuário **OC** for selecionado.</span><span class="sxs-lookup"><span data-stu-id="0f740-175">This action is available only when user agent **OC** is selected.</span></span>

  - <span data-ttu-id="0f740-p110">**Bloquear com URL** Impede que o cliente faça logon e exibe uma mensagem sobre onde baixar outra versão do cliente. Especifique o URL no campo  **URL**.</span><span class="sxs-lookup"><span data-stu-id="0f740-p110">**Block with URL** prevents the client from logging on and displays a message about where to download another client version. You specify the URL in the **URL** field.</span></span>

<span data-ttu-id="0f740-178">Para obter detalhes sobre a interoperabilidade entre clientes e versões de cliente, consulte [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="0f740-178">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="0f740-179">Para obter detalhes sobre como trabalhar com as configurações de versão de cliente, consulte [modificar a ação padrão para clientes não explicitamente suportados ou restritos](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="0f740-179">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

