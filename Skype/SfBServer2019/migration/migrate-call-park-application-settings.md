---
title: Migrar configurações do aplicativo do Estacionamento de Chamada
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'A migração do aplicativo Estacionamento de Chamada inclui o provisionamento do pool do Skype for Business Server 2019 com qualquer música personalizada em espera que tenha sido carregada na instalação herdada, restaurando as configurações de nível de serviço e retargendo todas as órbitas do Estacionamento de Chamadas para o pool do Skype for Business Server 2019. Se arquivos de música de espera personalizados foram configurados no pool, esses arquivos precisam ser copiados para o novo pool do Skype for Business Server 2019. Além disso, é recomendável que você faça backup de todos os arquivos de música de espera personalizados do Estacionamento de Chamada de outro destino para manter uma cópia de backup separada de todos os arquivos de música de espera personalizados que foram carregados para o Estacionamento de Chamada. Os arquivos de música de espera personalizados para o aplicativo Estacionamento de Chamada são armazenados no armazenamento de arquivos do pool. Para copiar os arquivos de áudio de um armazenamento de arquivos de pool para um armazenamento de arquivos do Skype for Business Server 2019, use o comando Xcopy com os seguintes parâmetros:'
ms.openlocfilehash: ded38ab600da4b277b1cdc83218833c26df081aa
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752813"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="fd7c1-107">Migrar configurações do aplicativo do Estacionamento de Chamada</span><span class="sxs-lookup"><span data-stu-id="fd7c1-107">Migrate Call Park application settings</span></span>

<span data-ttu-id="fd7c1-108">A migração do aplicativo Estacionamento de Chamada inclui o provisionamento do pool do Skype for Business Server 2019 com qualquer arquivo de música de espera personalizado que tenha sido carregado na instalação herdada, restaurando as configurações de nível de serviço e direcionando todas as órbitas de Estacionamento de Chamadas para o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="fd7c1-108">The migration of the Call Park application includes provisioning the Skype for Business Server 2019 pool with any custom music-on-hold files that have been uploaded in the legacy install, restoring the service-level settings and re-targeting all Call Park orbits to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="fd7c1-109">Se arquivos de música de espera personalizados foram configurados no pool, esses arquivos precisam ser copiados para o novo pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="fd7c1-109">If customized music-on-hold files have been configured in the pool, these files need to be copied to the new Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="fd7c1-110">Além disso, é recomendável que você faça backup de todos os arquivos de música de espera personalizadas do Estacionamento de Chamada em outro destino para manter uma cópia de backup separada de qualquer arquivo de música de espera personalizado que tenha sido carregado para o Estacionamento de Chamada.</span><span class="sxs-lookup"><span data-stu-id="fd7c1-110">Additionally, it is recommended that you back up any Call Park customized music-on-hold files to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="fd7c1-111">Os arquivos de música de espera personalizados para o aplicativo Estacionamento de Chamada são armazenados no armazenamento de arquivos do pool.</span><span class="sxs-lookup"><span data-stu-id="fd7c1-111">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="fd7c1-112">Para copiar os arquivos de áudio de um armazenamento de arquivos de pool para um armazenamento de arquivos do Skype for Business Server 2019, use o comando **Xcopy** com os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="fd7c1-112">To copy the audio files from a pool file store to a Skype for Business Server 2019 file store, use the **Xcopy** command with the following parameters:</span></span> 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

<span data-ttu-id="fd7c1-113">Quando todos os arquivos de áudio personalizados são copiados para o armazenamento de arquivos do Skype for Business Server 2019, as configurações do aplicativo Estacionamento de Chamada do pool do Skype for Business Server 2019 devem ser configuradas, e os intervalos de órbita do Estacionamento de Chamadas associados ao pool herdado devem ser reatribuídos ao pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="fd7c1-113">When all customized audio files have been copied to the Skype for Business Server 2019 file store, the Call Park application settings of the Skype for Business Server 2019 pool must be configured, and the Call Park orbit ranges that are associated with the legacy pool must be reassigned to the Skype for Business Server 2019 pool.</span></span>

<span data-ttu-id="fd7c1-114">As configurações do aplicativo Estacionamento de Chamada incluem o limite de tempo limite de retirada, a habilitação ou desabilitação de música em espera, o máximo de tentativas de atendimento de chamada e a solicitação de tempo limite.</span><span class="sxs-lookup"><span data-stu-id="fd7c1-114">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts, and the timeout request.</span></span> <span data-ttu-id="fd7c1-115">Você deve gerenciar as configurações do aplicativo Estacionamento de Chamadas usando o Shell de Gerenciamento do Skype for Business Server para executar o cmdlet **Set-CsCpsConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="fd7c1-115">You must manage Call Park application settings by using the Skype for Business Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="fd7c1-116">Você não pode gerenciar as configurações do aplicativo Estacionamento de Chamadas usando o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fd7c1-116">You cannot manage the Call Park application settings using the Skype for Business Server Control Panel.</span></span> 

## <a name="reconfigure-the-call-park-service-settings"></a><span data-ttu-id="fd7c1-117">Reconfigurar as Configurações do Serviço de Estacionamento de Chamada</span><span class="sxs-lookup"><span data-stu-id="fd7c1-117">Reconfigure the Call Park Service Settings</span></span>

1. <span data-ttu-id="fd7c1-118">No Servidor front-end do Skype for Business Server 2019, abra o Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fd7c1-118">From the Skype for Business Server 2019 Front End Server, open the Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="fd7c1-119">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fd7c1-119">At the command line, type the following:</span></span>

    > [!NOTE]
    > <span data-ttu-id="fd7c1-120">Se as configurações do aplicativo Estacionamento de Chamada do Skype for Business Server 2019 são idênticas às configurações herdada, ignore esta etapa.</span><span class="sxs-lookup"><span data-stu-id="fd7c1-120">If your Skype for Business Server 2019 Call Park application settings are identical to the legacy settings, you can skip this step.</span></span> <span data-ttu-id="fd7c1-121">Se as configurações do aplicativo Estacionamento de Chamada são diferentes para o Skype for Business Server 2019 e ambientes herdados, use o cmdlet abaixo como um modelo para atualizar essas alterações.</span><span class="sxs-lookup"><span data-stu-id="fd7c1-121">If Call Park application settings are different for the Skype for Business Server 2019 and legacy environments, use the cmdlet below as a template to update those changes.</span></span> 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

<span data-ttu-id="fd7c1-122">Para reatribuir todos os intervalos de órbitas do Estacionamento de Chamadas do pool herdado para o pool do Skype for Business Server 2019, você pode usar o Painel de Controle do Skype for Business Server ou o Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fd7c1-122">To reassign all Call Park orbit ranges from the legacy pool to the Skype for Business Server 2019 pool, you can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a><span data-ttu-id="fd7c1-123">Reatribuir todos os intervalos de órbita de estacionamento de chamada usando o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fd7c1-123">Reassign all Call Park Orbit Ranges using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="fd7c1-124">Abra o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fd7c1-124">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="fd7c1-125">No painel esquerdo, selecione Recursos **de Voz.**</span><span class="sxs-lookup"><span data-stu-id="fd7c1-125">In the left pane, select **Voice Features**.</span></span>

3. <span data-ttu-id="fd7c1-126">Selecione a **guia Estacionamento de** Chamada.</span><span class="sxs-lookup"><span data-stu-id="fd7c1-126">Select the **Call Park** tab.</span></span> 

4. <span data-ttu-id="fd7c1-127">Para cada intervalo de órbita de Estacionamento de Chamadas atribuído a um pool herdado, edite o **FQDN** da configuração do servidor de destino e selecione o pool do Skype for Business Server 2019 que processará as solicitações de Estacionamento de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="fd7c1-127">For each Call Park orbit range assigned to a legacy pool, edit the **FQDN of destination server** setting and select the Skype for Business Server 2019 pool that will process the Call Park requests.</span></span> 

5. <span data-ttu-id="fd7c1-128">Selecione **Confirmação** para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="fd7c1-128">Select **Commit** to save the changes.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a><span data-ttu-id="fd7c1-129">Reatribuir todos os intervalos de órbitas de estacionamento de chamada usando o Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fd7c1-129">Reassign all Call Park Orbit Ranges using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="fd7c1-130">Abra o Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fd7c1-130">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="fd7c1-131">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fd7c1-131">At the command line, type the following:</span></span>

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    <span data-ttu-id="fd7c1-132">Este cmdlet lista todos os intervalos de órbitas do Estacionamento de Chamada na implantação.</span><span class="sxs-lookup"><span data-stu-id="fd7c1-132">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="fd7c1-133">Todas as órbitas de Estacionamento de Chamada que tenham os parâmetros **CallParkServiceId** e **CallParkServerFqdn** definidos como o pool herdado devem ser reatribuídos.</span><span class="sxs-lookup"><span data-stu-id="fd7c1-133">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the legacy pool must be reassigned.</span></span> 

    <span data-ttu-id="fd7c1-134">Para reatribuir os intervalos de órbita do Estacionamento de Chamadas herdados ao pool do Skype for Business Server 2019, na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fd7c1-134">To reassign the legacy Call Park orbit ranges to the Skype for Business Server 2019 pool, at the command line, type the following:</span></span>

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

<span data-ttu-id="fd7c1-135">Depois de reatribuir todos os intervalos de órbitas do Estacionamento de Chamadas ao pool do Skype for Business Server 2019, o processo de migração para o aplicativo Estacionamento de Chamadas será concluído e o pool do Skype for Business Server 2019 lidará com todas as solicitações futuras de Estacionamento de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="fd7c1-135">After reassigning all Call Park orbit ranges to the Skype for Business Server 2019 pool, the migration process for the Call Park application will be completed and the Skype for Business Server 2019 pool will handle all future Call Park requests.</span></span>


