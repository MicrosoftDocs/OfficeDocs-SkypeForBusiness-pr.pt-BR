---
title: Provisionamento remoto e entrada para dispositivos Android do Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: prgholve
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como provisionar e entrar remotamente em dispositivos Teams Android
ms.openlocfilehash: 43a025c0cc68fb7f10015d69298f8dd75f9003e8
ms.sourcegitcommit: 95386369e2256ba382b4d6e34adb7473de050b26
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/29/2021
ms.locfileid: "51410319"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a><span data-ttu-id="fdaf0-103">Provisionamento remoto e entrada para dispositivos Android do Teams</span><span class="sxs-lookup"><span data-stu-id="fdaf0-103">Remote provisioning and sign in for Teams Android devices</span></span>

<span data-ttu-id="fdaf0-104">Os administradores de IT podem provisionar e entrar remotamente em um dispositivo Teams Android.</span><span class="sxs-lookup"><span data-stu-id="fdaf0-104">IT admins can remotely provision and sign in to a Teams Android device.</span></span> <span data-ttu-id="fdaf0-105">Para provisionar um dispositivo remotamente, o administrador precisa carregar as IDs MAC dos dispositivos que estão sendo provisionados e criar um código de verificação.</span><span class="sxs-lookup"><span data-stu-id="fdaf0-105">To provision a device remotely, the admin needs to upload the MAC IDs of the devices being provisioned and create a verification code.</span></span> <span data-ttu-id="fdaf0-106">Todo o processo pode ser concluído remotamente a partir do Centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="fdaf0-106">The entire process can be completed remotely from the Teams admin center.</span></span>

## <a name="review-the-supported-devices"></a><span data-ttu-id="fdaf0-107">Revisar os dispositivos com suporte</span><span class="sxs-lookup"><span data-stu-id="fdaf0-107">Review the supported devices</span></span>

<span data-ttu-id="fdaf0-108">A lista a seguir mostra os requisitos de firmware de dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="fdaf0-108">The following list shows the Android device firmware requirements.</span></span>

|<span data-ttu-id="fdaf0-109">Categoria de dispositivo</span><span class="sxs-lookup"><span data-stu-id="fdaf0-109">Device category</span></span>|<span data-ttu-id="fdaf0-110">Modelo de dispositivo</span><span class="sxs-lookup"><span data-stu-id="fdaf0-110">Device model</span></span>|<span data-ttu-id="fdaf0-111">Versão do firmware</span><span class="sxs-lookup"><span data-stu-id="fdaf0-111">Firmware version</span></span>|
|-|-|-|
|<span data-ttu-id="fdaf0-112">Telefones do Teams</span><span class="sxs-lookup"><span data-stu-id="fdaf0-112">Teams phones</span></span>|<span data-ttu-id="fdaf0-113">Yealink T55/T56/T58</span><span class="sxs-lookup"><span data-stu-id="fdaf0-113">Yealink T55/T56/T58</span></span>|<span data-ttu-id="fdaf0-114">58.15.0.124</span><span class="sxs-lookup"><span data-stu-id="fdaf0-114">58.15.0.124</span></span>|
|<span data-ttu-id="fdaf0-115">Telefones do Teams</span><span class="sxs-lookup"><span data-stu-id="fdaf0-115">Teams phones</span></span>|<span data-ttu-id="fdaf0-116">Yealink VP59</span><span class="sxs-lookup"><span data-stu-id="fdaf0-116">Yealink VP59</span></span>|<span data-ttu-id="fdaf0-117">91.15.0.58</span><span class="sxs-lookup"><span data-stu-id="fdaf0-117">91.15.0.58</span></span>|
|<span data-ttu-id="fdaf0-118">Telefones do Teams</span><span class="sxs-lookup"><span data-stu-id="fdaf0-118">Teams phones</span></span>|<span data-ttu-id="fdaf0-119">Yealink CP960</span><span class="sxs-lookup"><span data-stu-id="fdaf0-119">Yealink CP960</span></span>|<span data-ttu-id="fdaf0-120">73.15.0.117</span><span class="sxs-lookup"><span data-stu-id="fdaf0-120">73.15.0.117</span></span>|
|<span data-ttu-id="fdaf0-121">Telefones do Teams</span><span class="sxs-lookup"><span data-stu-id="fdaf0-121">Teams phones</span></span>|<span data-ttu-id="fdaf0-122">Yealink MP56/MP54/MP58</span><span class="sxs-lookup"><span data-stu-id="fdaf0-122">Yealink MP56/MP54/MP58</span></span>|<span data-ttu-id="fdaf0-123">122.15.0.36</span><span class="sxs-lookup"><span data-stu-id="fdaf0-123">122.15.0.36</span></span>|
|<span data-ttu-id="fdaf0-124">Telefones do Teams</span><span class="sxs-lookup"><span data-stu-id="fdaf0-124">Teams phones</span></span>|<span data-ttu-id="fdaf0-125">Crestron UC-2</span><span class="sxs-lookup"><span data-stu-id="fdaf0-125">Crestron UC-2</span></span>|<span data-ttu-id="fdaf0-126">1.0.3.52</span><span class="sxs-lookup"><span data-stu-id="fdaf0-126">1.0.3.52</span></span>|

## <a name="add-a-device-mac-address"></a><span data-ttu-id="fdaf0-127">Adicionar um endereço MAC de dispositivo</span><span class="sxs-lookup"><span data-stu-id="fdaf0-127">Add a device MAC address</span></span>

<span data-ttu-id="fdaf0-128">Conclua as etapas a seguir para provisionar um novo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fdaf0-128">Complete the following steps to provision a new device.</span></span>

1. <span data-ttu-id="fdaf0-129">Entre no Centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="fdaf0-129">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="fdaf0-130">Expanda **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="fdaf0-130">Expand **Devices**.</span></span>
3. <span data-ttu-id="fdaf0-131">Selecione **Provisionr novo dispositivo** na guia **Ações.**</span><span class="sxs-lookup"><span data-stu-id="fdaf0-131">Select **Provision new device** from the **Actions** tab.</span></span>

<span data-ttu-id="fdaf0-132">Na janela **Provisionar novos dispositivos,** você pode adicionar o endereço MAC manualmente ou carregar um arquivo.</span><span class="sxs-lookup"><span data-stu-id="fdaf0-132">In the **Provision new devices** window, you can either add the MAC address manually or upload a file.</span></span>

### <a name="manually-add-a-device-mac-address"></a><span data-ttu-id="fdaf0-133">Adicionar manualmente um endereço MAC de dispositivo</span><span class="sxs-lookup"><span data-stu-id="fdaf0-133">Manually add a device MAC address</span></span>

1. <span data-ttu-id="fdaf0-134">Na guia **Aguardando ativação,** selecione **Adicionar ID MAC**.</span><span class="sxs-lookup"><span data-stu-id="fdaf0-134">From the **Awaiting Activation** tab, select **Add MAC ID**.</span></span>

   ![adicionar manualmente um endereço mac de dispositivo](../media/remote-provision-6.png)

1. <span data-ttu-id="fdaf0-136">Insira a ID MAC.</span><span class="sxs-lookup"><span data-stu-id="fdaf0-136">Enter the MAC ID.</span></span>
1. <span data-ttu-id="fdaf0-137">Insira um local, que ajuda os técnicos a identificar onde instalar os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fdaf0-137">Enter a location, which helps technicians identify where to install the devices.</span></span>
1. <span data-ttu-id="fdaf0-138">Selecione **Aplicar** quando concluído.</span><span class="sxs-lookup"><span data-stu-id="fdaf0-138">Select **Apply** when finished.</span></span>

### <a name="upload-a-file-to-add-a-device-mac-address"></a><span data-ttu-id="fdaf0-139">Carregar um arquivo para adicionar um endereço MAC do dispositivo</span><span class="sxs-lookup"><span data-stu-id="fdaf0-139">Upload a file to add a device MAC address</span></span>

1. <span data-ttu-id="fdaf0-140">Na guia **Aguardando ativação,** selecione **Carregar IDs MAC**.</span><span class="sxs-lookup"><span data-stu-id="fdaf0-140">From the **Awaiting Activation** tab, select **Upload MAC IDs**.</span></span>
2. <span data-ttu-id="fdaf0-141">Baixe o modelo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="fdaf0-141">Download the file template.</span></span>
3. <span data-ttu-id="fdaf0-142">Insira a ID mac e o local e salve o arquivo.</span><span class="sxs-lookup"><span data-stu-id="fdaf0-142">Enter the MAC ID and location, and then save the file.</span></span>
4. <span data-ttu-id="fdaf0-143">**Selecione o arquivo** e selecione **Carregar**.</span><span class="sxs-lookup"><span data-stu-id="fdaf0-143">**Select file**, and then select **Upload**.</span></span>

## <a name="generate-a-verification-code"></a><span data-ttu-id="fdaf0-144">Gerar um código de verificação</span><span class="sxs-lookup"><span data-stu-id="fdaf0-144">Generate a verification code</span></span>

<span data-ttu-id="fdaf0-145">Você precisa de um código de verificação para os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fdaf0-145">You need a verification code for the devices.</span></span> <span data-ttu-id="fdaf0-146">O código de verificação é gerado em massa ou no nível do dispositivo e é válido por 24 horas.</span><span class="sxs-lookup"><span data-stu-id="fdaf0-146">The verification code is generated in bulk or at the device level and is valid for 24 hours.</span></span>

1. <span data-ttu-id="fdaf0-147">Na guia **Aguardando ativação,** selecione uma ID MAC existente.</span><span class="sxs-lookup"><span data-stu-id="fdaf0-147">From the **Awaiting Activation** tab, select an existing MAC ID.</span></span>
   <span data-ttu-id="fdaf0-148">Uma senha é criada para o endereço MAC e é mostrada na coluna **Código de** Verificação.</span><span class="sxs-lookup"><span data-stu-id="fdaf0-148">A password is created for the MAC address and is shown in the **Verification Code** column.</span></span>

2. <span data-ttu-id="fdaf0-149">Forneça a lista de IDs MAC e códigos de verificação para os técnicos de campo.</span><span class="sxs-lookup"><span data-stu-id="fdaf0-149">Provide the list of MAC IDs and verification codes to the field technicians.</span></span> <span data-ttu-id="fdaf0-150">Você pode exportar os detalhes diretamente em um arquivo e compartilhar o arquivo com o técnico que está fazendo o trabalho de instalação real.</span><span class="sxs-lookup"><span data-stu-id="fdaf0-150">You can export the detail directly in a file and share the file with the technician who is doing the actual installation work.</span></span>

## <a name="provision-the-device"></a><span data-ttu-id="fdaf0-151">Provisione o dispositivo</span><span class="sxs-lookup"><span data-stu-id="fdaf0-151">Provision the device</span></span>

<span data-ttu-id="fdaf0-152">Quando o dispositivo é ligado e conectado à rede, o técnico provisiona o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fdaf0-152">When the device is powered on and connected to the network, the technician provisions the device.</span></span> <span data-ttu-id="fdaf0-153">Essas etapas são concluídas no dispositivo Teams.</span><span class="sxs-lookup"><span data-stu-id="fdaf0-153">These steps are completed on the Teams device.</span></span>

1. <span data-ttu-id="fdaf0-154">O técnico seleciona **Dispositivo de provisionamento** nas **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="fdaf0-154">The technician selects **Provision device** from the **Settings**.</span></span>  

   ![Provisione a nova opção de dispositivo na guia Ações](../media/provision-device1.png)
  
2. <span data-ttu-id="fdaf0-156">O técnico ins fornece o código de verificação específico do dispositivo no campo de entrada fornecido.</span><span class="sxs-lookup"><span data-stu-id="fdaf0-156">The technician enters the device-specific verification code in the provided input field.</span></span>

   ![Provisione a verificação de novo dispositivo](../media/provision-device-verification1.png)

   <span data-ttu-id="fdaf0-158">Depois que o dispositivo for provisionado com êxito, o nome do locatário será exibido na página de entrada.</span><span class="sxs-lookup"><span data-stu-id="fdaf0-158">Once the device is provisioned successfully, the tenant name appears on the sign-in page.</span></span>

   ![Nome do locatário na página de login](../media/provision-code.png)

## <a name="sign-in-remotely"></a><span data-ttu-id="fdaf0-160">Entrar remotamente</span><span class="sxs-lookup"><span data-stu-id="fdaf0-160">Sign in remotely</span></span>

<span data-ttu-id="fdaf0-161">O dispositivo provisionado aparece na guia **Aguardando** entrada. Inicie o processo de entrada remota selecionando o dispositivo individual.</span><span class="sxs-lookup"><span data-stu-id="fdaf0-161">The provisioned device appears in the **Awaiting sign in** tab. Start the remote sign-in process by selecting the individual device.</span></span>

1. <span data-ttu-id="fdaf0-162">Selecione um dispositivo na guia **Aguardando entrada.**</span><span class="sxs-lookup"><span data-stu-id="fdaf0-162">Select a device from the **Awaiting sign in** tab.</span></span>

   ![A janela com uma lista de dispositivos prontos para entrar.](../media/remote-device1.png)

2. <span data-ttu-id="fdaf0-164">Siga as instruções em **Entrar em um usuário** e selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="fdaf0-164">Follow the instructions in **Sign in a user**, and then select **Close**.</span></span>

   ![a janela Entrar em um usuário para dispositivos individuais](../media/sign-in-user.png)

## <a name="related-article"></a><span data-ttu-id="fdaf0-166">Artigo relacionado</span><span class="sxs-lookup"><span data-stu-id="fdaf0-166">Related article</span></span>

- [<span data-ttu-id="fdaf0-167">Gerenciar seus dispositivos no Teams</span><span class="sxs-lookup"><span data-stu-id="fdaf0-167">Manage your devices in Teams</span></span>](device-management.md)
- [<span data-ttu-id="fdaf0-168">Atualizar dispositivos do Teams remotamente</span><span class="sxs-lookup"><span data-stu-id="fdaf0-168">Update Teams devices remotely</span></span>](remote-update.md)
