---
title: Visão geral do controle de política do Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: majaisin
description: Uma visão geral dos controles de política do Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1a4b0dcc52b5c497d594a26fda09f3f48b1c563a
ms.sourcegitcommit: 17d0108fb4d36a3f56144460683f53d77a8a0a7f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52777892"
---
# <a name="policy-control-overview-for-microsoft-teams"></a><span data-ttu-id="a18ec-103">Visão geral do controle de política do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a18ec-103">Policy control overview for Microsoft Teams</span></span>

<span data-ttu-id="a18ec-104">A Microsoft tem o compromisso de fornecer informações e controles necessários para você fazer escolhas sobre como os dados são coletados e usados ao usar o Microsoft Teams, uma parte do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a18ec-104">Microsoft is committed to providing you with the information and controls you need to make choices about how your data is collected and used when you’re using Microsoft Teams, a part of Microsoft 365.</span></span>

<span data-ttu-id="a18ec-105">Este artigo tem como objetivo fornecer informações sobre os controles de privacidade nas seguintes áreas:</span><span class="sxs-lookup"><span data-stu-id="a18ec-105">This article is intended to provide you with information about privacy controls for the following areas:</span></span>

- <span data-ttu-id="a18ec-106">**Dados de diagnóstico** sobre o Teams e o software do Office sendo usados ​​em computadores que executam o Windows em sua organização são coletados e enviados à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a18ec-106">**Diagnostic data** that is collected and sent to Microsoft about Teams and Office software being used on computers running Windows in your organization.</span></span>
- <span data-ttu-id="a18ec-107">**Experiências conectadas** que usam funcionalidade baseada em nuvem para fornecer recursos avançados do Teams e do Office para você e seus usuários.</span><span class="sxs-lookup"><span data-stu-id="a18ec-107">**Connected experiences** that use cloud-based functionality to provide enhanced Teams and Office features to you and your users.</span></span>

<span data-ttu-id="a18ec-108">Como parte dessas mudanças, haverá elementos novos e atualizados da interface do usuário (IU) e configurações de política</span><span class="sxs-lookup"><span data-stu-id="a18ec-108">As part of these changes, there are new and updated user interface (UI) elements and policy settings</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a18ec-109">Para obter mais informações, confira o conteúdo da [Visão Geral do Controle de Política](/deployoffice/privacy/overview-privacy-controls) do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a18ec-109">For further reading, please review the [Policy Control Overview](/deployoffice/privacy/overview-privacy-controls) content for Microsoft 365.</span></span>

## <a name="diagnostic-data-sent-from-microsoft-365-apps-for-enterprise-to-microsoft"></a><span data-ttu-id="a18ec-110">Dados de diagnóstico enviados do Microsoft 365 Apps para Grandes Empresas para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="a18ec-110">Diagnostic data sent from Microsoft 365 Apps for enterprise to Microsoft</span></span>

<span data-ttu-id="a18ec-111">Os dados de diagnóstico são usados para:</span><span class="sxs-lookup"><span data-stu-id="a18ec-111">Diagnostic data is used to:</span></span>

- <span data-ttu-id="a18ec-112">Manter o Teams seguro e atualizado.</span><span class="sxs-lookup"><span data-stu-id="a18ec-112">Keep Teams secure and up-to-date.</span></span>
- <span data-ttu-id="a18ec-113">Detectar, diagnosticar e corrigir problemas.</span><span class="sxs-lookup"><span data-stu-id="a18ec-113">Detect, diagnose, and remediate problems.</span></span>
- <span data-ttu-id="a18ec-114">Melhorar o produto.</span><span class="sxs-lookup"><span data-stu-id="a18ec-114">Make product improvements.</span></span>

<span data-ttu-id="a18ec-115">Um exemplo de alguns dos dados coletados inclui:</span><span class="sxs-lookup"><span data-stu-id="a18ec-115">An example of some of the collected data includes:</span></span>

- <span data-ttu-id="a18ec-116">Idioma do aplicativo</span><span class="sxs-lookup"><span data-stu-id="a18ec-116">Application language</span></span>
- <span data-ttu-id="a18ec-117">Tipo de usuário</span><span class="sxs-lookup"><span data-stu-id="a18ec-117">User type</span></span>
- <span data-ttu-id="a18ec-118">Versão do build do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="a18ec-118">Build version of the OS</span></span>

## <a name="clients-that-adhere-to-diagnostic-controls"></a><span data-ttu-id="a18ec-119">Clientes que aderem aos controles de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="a18ec-119">Clients that adhere to diagnostic controls</span></span>

<span data-ttu-id="a18ec-120">Os seguintes clientes aderem aos controles de diagnóstico e enviarão dados:</span><span class="sxs-lookup"><span data-stu-id="a18ec-120">The following clients adhere to diagnostic controls and will submit data:</span></span>

- <span data-ttu-id="a18ec-121">iOS</span><span class="sxs-lookup"><span data-stu-id="a18ec-121">iOS</span></span>
- <span data-ttu-id="a18ec-122">Android</span><span class="sxs-lookup"><span data-stu-id="a18ec-122">Android</span></span>
- <span data-ttu-id="a18ec-123">Área de trabalho (somente o componente que está usando a API do Win32)</span><span class="sxs-lookup"><span data-stu-id="a18ec-123">Desktop (only the component that is using the win32 API)</span></span>

<span data-ttu-id="a18ec-124">Para ver uma lista de eventos de dados de diagnóstico necessários e suas propriedades, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="a18ec-124">To see a list of required diagnostic data events and their properties, see the following articles:</span></span>

- [<span data-ttu-id="a18ec-125">Dados de diagnóstico móvel necessários para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a18ec-125">Required mobile diagnostic data for Microsoft Teams</span></span>](policy-control-diagnostic-data-mobile.md)
- [<span data-ttu-id="a18ec-126">Dados necessários de diagnóstico da área de trabalho para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a18ec-126">Required desktop diagnostic data for Microsoft Teams</span></span>](policy-control-diagnostic-data-desktop.md)

## <a name="diagnostic-data-sent-from-the-teams-app-to-microsoft"></a><span data-ttu-id="a18ec-127">Dados de diagnóstico enviados do aplicativo Teams para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="a18ec-127">Diagnostic data sent from the Teams app to Microsoft</span></span>

<span data-ttu-id="a18ec-128">Esses dados de diagnóstico sobre o software do Teams sendo usado ​​em computadores que executam o Windows em sua organização são coletados e enviados à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a18ec-128">This diagnostic data is collected and sent to Microsoft about Teams software being used on computers running Windows in your organization.</span></span>

<span data-ttu-id="a18ec-129">Há três níveis de dados de diagnóstico para o software do Teams que você pode escolher:</span><span class="sxs-lookup"><span data-stu-id="a18ec-129">There are three levels of diagnostic data for Teams software that you can choose from:</span></span>

- <span data-ttu-id="a18ec-130">**Obrigatório** Os dados mínimos necessários para ajudar a manter o Office seguro, atualizado e funcionando conforme o esperado no dispositivo em que está instalado.</span><span class="sxs-lookup"><span data-stu-id="a18ec-130">**Required** The minimum data necessary to help keep Office secure, up-to-date, and performing as expected on the device it’s installed on.</span></span>
- <span data-ttu-id="a18ec-131">**Opcional** Dados opcionais que nos ajudam a melhorar o produto e fornecem informações aprimoradas para nos ajudar a detectar, diagnosticar e corrigir problemas.</span><span class="sxs-lookup"><span data-stu-id="a18ec-131">**Optional** Additional data that helps us make product improvements and provides enhanced information to help us detect, diagnose, and remediate issues.</span></span>
- <span data-ttu-id="a18ec-132">**Nenhum** Nenhum dado de diagnóstico sobre o software do Teams em execução no dispositivo do usuário é coletado e enviado para nós.</span><span class="sxs-lookup"><span data-stu-id="a18ec-132">**Neither** No diagnostic data about Teams software running on the user’s device is collected and sent to us.</span></span> <span data-ttu-id="a18ec-133">Essa opção, no entanto, limita significativamente nossa capacidade de detectar, diagnosticar e corrigir problemas que seus usuários podem encontrar usando o Teams.</span><span class="sxs-lookup"><span data-stu-id="a18ec-133">This option, however, significantly limits our ability to detect, diagnose, and remediate problems your users may encounter using Teams.</span></span>

<span data-ttu-id="a18ec-134">Os dados de diagnóstico obrigatórios podem incluir, por exemplo, informações sobre a versão do cliente Teams instalado no dispositivo ou incluir informações que indicam que o aplicativo Teams está falhando ao tentar ingressar em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="a18ec-134">Required diagnostic data could include, for example, information about the version of Teams client installed on the device, or include information that indicates that the Teams application is crashing when trying to join a meeting.</span></span> <span data-ttu-id="a18ec-135">Os dados de diagnóstico opcionais podem incluir informações sobre o tempo que leva para iniciar uma chamada telefônica, o que pode indicar um problema de conectividade ou desempenho da rede.</span><span class="sxs-lookup"><span data-stu-id="a18ec-135">Optional diagnostic data could include information about the time it takes to initiate a phone call, which could indicate an issue with connectivity or network performance.</span></span>

<span data-ttu-id="a18ec-136">Se você optar por nos enviar dados de diagnóstico opcionais, os dados de diagnóstico obrigatórios também serão incluídos.</span><span class="sxs-lookup"><span data-stu-id="a18ec-136">If you choose to send us optional diagnostic data, required diagnostic data is also included.</span></span>

<span data-ttu-id="a18ec-137">Como administrador da sua organização, você poderá usar uma configuração de política para escolher o nível de dados de diagnóstico que será enviado para nós.</span><span class="sxs-lookup"><span data-stu-id="a18ec-137">As an admin for your organization, you’ll be able to use a policy setting to choose which level of diagnostic data is sent to us.</span></span> <span data-ttu-id="a18ec-138">Dados diagnósticos opcionais serão enviados à Microsoft, a menos que você altere a configuração.</span><span class="sxs-lookup"><span data-stu-id="a18ec-138">Optional diagnostic data will be sent to Microsoft unless you change the setting.</span></span> <span data-ttu-id="a18ec-139">O fornecimento de dados de diagnóstico opcionais permite que a equipe de engenharia do Office na Microsoft detecte, diagnostique e atenue os problemas para reduzir os impactos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="a18ec-139">Providing optional diagnostic data better enables the Office engineering team at Microsoft to detect, diagnose, and mitigate issues to reduce impacts to your organization.</span></span> 

<span data-ttu-id="a18ec-140">Para escolher que nível de dados de diagnóstico são enviados para nós, use o [serviço de política de nuvem do Office](/deployoffice/overview-office-cloud-policy-service) e defina a configuração da política *Configurar o nível de dados de diagnóstico de software cliente enviados pelo Office para a Microsoft*.</span><span class="sxs-lookup"><span data-stu-id="a18ec-140">To choose which level of diagnostic data is sent to us, use the [Office cloud policy service](/deployoffice/overview-office-cloud-policy-service) and configure the *Configure the level of client software diagnostic data sent by Office to Microsoft* policy setting.</span></span> <span data-ttu-id="a18ec-141">Essa é a mesma configuração de política usada para configurar que nível de dados de diagnóstico são enviados por outros aplicativos do Office (como Word, Excel e PowerPoint) que vêm com os Aplicativos do Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="a18ec-141">This is the same policy setting that is used to configure which level of diagnostic data is sent by other Office apps (such as Word, Excel, and PowerPoint) that come with Microsoft 365 Apps for enterprise.</span></span>

<span data-ttu-id="a18ec-142">Os usuários não poderão alterar o nível de dados de diagnóstico de seus dispositivos se eles estiverem conectados ao Teams com suas credenciais organizacionais, que às vezes são chamadas de conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="a18ec-142">Your users won’t be able to change the diagnostic data level for their devices if they are signed in to Teams with their organizational credentials, which is sometimes referred to as a work or school account.</span></span>

<span data-ttu-id="a18ec-143">Esses dados de diagnóstico não incluem nomes de usuários, seus endereços de email ou o conteúdo de seus arquivos do Office.</span><span class="sxs-lookup"><span data-stu-id="a18ec-143">This diagnostic data doesn’t include names of users, their email addresses, or the content of their Office files.</span></span> <span data-ttu-id="a18ec-144">Nosso sistema cria uma ID exclusiva que é associada a dados de diagnóstico do usuário.</span><span class="sxs-lookup"><span data-stu-id="a18ec-144">Our system creates a unique ID that it associates with your user’s diagnostic data.</span></span> <span data-ttu-id="a18ec-145">Quando recebemos dados de diagnóstico mostrando que o aplicativo Teams falhou 100 vezes, essa ID exclusiva nos permite determinar se foi um único usuário que teve esse problema 100 vezes ou se foi o aplicativo de 100 usuários que falhou uma vez.</span><span class="sxs-lookup"><span data-stu-id="a18ec-145">When we receive diagnostic data showing that the Teams app crashed 100 times, this unique ID lets us determine if it was a single user who crashed 100 times or if it was 100 different users who each crashed once.</span></span> <span data-ttu-id="a18ec-146">Não usamos essa ID exclusiva para identificar um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="a18ec-146">We don’t use this unique ID to identify a specific user.</span></span>

<span data-ttu-id="a18ec-147">Para ver quais dados de diagnóstico foram enviados à Microsoft, você poderá usar o Visualizador de Dados de Diagnóstico, que você pode baixar e instalar gratuitamente da Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="a18ec-147">To see what diagnostic data is being sent to Microsoft, you can use the Diagnostic Data Viewer, which you can download and install for free from the Microsoft Store.</span></span> <span data-ttu-id="a18ec-148">Para saber mais, consulte [Usando o Visualizador de Dados de Diagnóstico com o Office](https://support.microsoft.com/topic/cf761ce9-d805-4c60-a339-4e07f3182855).</span><span class="sxs-lookup"><span data-stu-id="a18ec-148">For more information, see [Using the Diagnostic Data Viewer with Office](https://support.microsoft.com/topic/cf761ce9-d805-4c60-a339-4e07f3182855).</span></span>

> [!NOTE]
> <span data-ttu-id="a18ec-149">O suporte para o Visualizador de Dados de Diagnóstico está disponível para Equipes em dispositivos com Android.</span><span class="sxs-lookup"><span data-stu-id="a18ec-149">Support for the Diagnostic Data Viewer is available for Teams on devices running Android.</span></span> <span data-ttu-id="a18ec-150">O suporte para Equipes em dispositivos com Windows, macOS ou iOS está sendo trabalhado.</span><span class="sxs-lookup"><span data-stu-id="a18ec-150">Support for Teams on devices running Windows, macOS, or iOS is being worked on.</span></span>

## <a name="required-service-data-for-connected-experiences"></a><span data-ttu-id="a18ec-151">Dados de serviço obrigatórios para experiências conectadas</span><span class="sxs-lookup"><span data-stu-id="a18ec-151">Required service data for connected experiences</span></span>

<span data-ttu-id="a18ec-152">Dados de serviço necessários são dados que nos permitem fornecer essas experiências conectadas baseadas em nuvem e que ajudam a tornar essas experiências seguras e a funcionarem conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="a18ec-152">Required service data is data that enables us to deliver these cloud-based connected experiences and help make these experiences secure and perform as expected.</span></span> <span data-ttu-id="a18ec-153">Você pode optar por não oferecer essa funcionalidade a seus usuários; nesse caso, essas informações não serão fornecidas à Microsoft para oferecer suporte à funcionalidade das experiências conectadas.</span><span class="sxs-lookup"><span data-stu-id="a18ec-153">You can choose to not offer this functionality to your users, in which case this information will not be provided to Microsoft to support the functionality of connected experiences.</span></span> <span data-ttu-id="a18ec-154">Você pode saber mais sobre os [dados de serviço obrigatórios](/deployoffice/privacy/required-service-data).</span><span class="sxs-lookup"><span data-stu-id="a18ec-154">You can learn more about [required service data](/deployoffice/privacy/required-service-data).</span></span>

## <a name="essential-services-for-microsoft-teams"></a><span data-ttu-id="a18ec-155">Serviços essenciais do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a18ec-155">Essential services for Microsoft Teams</span></span>

<span data-ttu-id="a18ec-156">Também há um conjunto de serviços que são essenciais para os aplicativos do Microsoft 365 Apps para Grandes Empresas e não podem ser desabilitados.</span><span class="sxs-lookup"><span data-stu-id="a18ec-156">There is also a set of services that are essential to how Microsoft 365 Apps for enterprise functions and cannot be disabled.</span></span> <span data-ttu-id="a18ec-157">Por exemplo, o serviço de licenciamento que confirma que você está corretamente licenciado para usar o Microsoft 365 Apps para Grandes Empresas.</span><span class="sxs-lookup"><span data-stu-id="a18ec-157">For example, the licensing service that confirms that you are properly licensed to use Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="a18ec-158">Os dados de serviço necessários sobre esses serviços são coletados e enviados à Microsoft, independentemente de qualquer outra configuração de política.</span><span class="sxs-lookup"><span data-stu-id="a18ec-158">Required service data about these services is collected and sent to Microsoft, regardless of any other policy settings that you have configured.</span></span>

<span data-ttu-id="a18ec-159">Para saber mais, confira [Serviços essenciais do Office](/deployoffice/privacy/essential-services).</span><span class="sxs-lookup"><span data-stu-id="a18ec-159">For more information, see [Essential services for Office](/deployoffice/privacy/essential-services).</span></span>