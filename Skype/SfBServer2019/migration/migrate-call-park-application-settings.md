---
title: Migrar configurações do aplicativo do Estacionamento de Chamada
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'A migração do aplicativo de estacionamento de chamadas inclui o provisionamento do pool do Skype for Business Server 2019 com qualquer música personalizada em arquivos de retenção que foram carregados na instalação herdada, a restauração das configurações de nível de serviço e o redirecionamento de todas as órbitas do estacionamento de chamada para o Pool do Skype for Business Server 2019. Se os arquivos de música em espera personalizados tiverem sido configurados no pool, esses arquivos precisarão ser copiados para o novo pool do Skype for Business Server 2019. Além disso, é recomendável que você faça backup de todos os arquivos de música em espera personalizados de qualquer telefone para outro destino para manter uma cópia de backup separada de todos os arquivos de música em espera personalizados que foram carregados para o parque da chamada. Os arquivos de música em espera personalizados para o aplicativo de estacionamento de chamadas são armazenados no repositório de arquivos do pool. Para copiar os arquivos de áudio de um repositório de arquivos de pool para um repositório de arquivos do Skype for Business Server 2019, use o comando xcopy com os seguintes parâmetros:'
ms.openlocfilehash: 0435144fc647a08d8252f35d8449d1e7daa62d68
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991156"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="8974a-107">Migrar configurações do aplicativo do Estacionamento de Chamada</span><span class="sxs-lookup"><span data-stu-id="8974a-107">Migrate Call Park application settings</span></span>

<span data-ttu-id="8974a-108">A migração do aplicativo de estacionamento de chamadas inclui o provisionamento do pool do Skype for Business Server 2019 com qualquer arquivo de música em espera personalizado que tenha sido carregado na instalação herdada, restauração das configurações do nível de serviço e redirecionamento de todas as órbitas do estacionamento de chamada ao pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8974a-108">The migration of the Call Park application includes provisioning the Skype for Business Server 2019 pool with any custom music-on-hold files that have been uploaded in the legacy install, restoring the service-level settings and re-targeting all Call Park orbits to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="8974a-109">Se os arquivos de música em espera personalizados tiverem sido configurados no pool, esses arquivos precisarão ser copiados para o novo pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8974a-109">If customized music-on-hold files have been configured in the pool, these files need to be copied to the new Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="8974a-110">Além disso, é recomendável que você faça backup de qualquer chamada personalizada em arquivos de música em espera para outro destino para manter uma cópia de backup separada de todos os arquivos de música em espera personalizados que foram carregados para o parque de chamadas.</span><span class="sxs-lookup"><span data-stu-id="8974a-110">Additionally, it is recommended that you back up any Call Park customized music-on-hold files to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="8974a-111">Os arquivos de música em espera personalizados para o aplicativo de estacionamento de chamadas são armazenados no repositório de arquivos do pool.</span><span class="sxs-lookup"><span data-stu-id="8974a-111">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="8974a-112">Para copiar os arquivos de áudio de um repositório de arquivos de pool para um repositório de arquivos do Skype for Business Server 2019, use o comando **xcopy** com os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="8974a-112">To copy the audio files from a pool file store to a Skype for Business Server 2019 file store, use the **Xcopy** command with the following parameters:</span></span> 

```
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

<span data-ttu-id="8974a-113">Quando todos os arquivos de áudio personalizados foram copiados para o repositório de arquivos do Skype for Business Server 2019, as configurações do aplicativo de estacionamento de chamada do pool do Skype for Business Server 2019 devem ser configuradas e os intervalos de estacionador de chamadas em órbita associados ao pool herdado deve ser reatribuído ao pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8974a-113">When all customized audio files have been copied to the Skype for Business Server 2019 file store, the Call Park application settings of the Skype for Business Server 2019 pool must be configured, and the Call Park orbit ranges that are associated with the legacy pool must be reassigned to the Skype for Business Server 2019 pool.</span></span>

<span data-ttu-id="8974a-114">As configurações do aplicativo de estacionamento de chamada incluem o limite de tempo limite de separação, habilitando ou desabilitando música em espera, o número máximo de tentativas de chamadas e a solicitação de tempo limite.</span><span class="sxs-lookup"><span data-stu-id="8974a-114">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts, and the timeout request.</span></span> <span data-ttu-id="8974a-115">Você deve gerenciar as configurações do aplicativo parque de chamadas usando o Shell de gerenciamento do Skype for Business Server para executar o cmdlet **set-CsCpsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="8974a-115">You must manage Call Park application settings by using the Skype for Business Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="8974a-116">Não é possível gerenciar as configurações do aplicativo parque de chamadas usando o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8974a-116">You cannot manage the Call Park application settings using the Skype for Business Server Control Panel.</span></span> 

## <a name="reconfigure-the-call-park-service-settings"></a><span data-ttu-id="8974a-117">Reconfigurar as configurações de serviço do estacionamento de chamada</span><span class="sxs-lookup"><span data-stu-id="8974a-117">Reconfigure the Call Park Service Settings</span></span>

1. <span data-ttu-id="8974a-118">No servidor front-end do Skype for Business Server 2019, abra o Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8974a-118">From the Skype for Business Server 2019 Front End Server, open the Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="8974a-119">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8974a-119">At the command line, type the following:</span></span>

    > [!NOTE]
    > <span data-ttu-id="8974a-120">Se as configurações do aplicativo parque de chamadas do Skype for Business Server 2019 forem idênticas às configurações herdadas, você poderá ignorar esta etapa.</span><span class="sxs-lookup"><span data-stu-id="8974a-120">If your Skype for Business Server 2019 Call Park application settings are identical to the legacy settings, you can skip this step.</span></span> <span data-ttu-id="8974a-121">Se as configurações do aplicativo de estacionamento de chamada forem diferentes para o Skype for Business Server 2019 e ambientes herdados, use o cmdlet abaixo como um modelo para atualizar essas alterações.</span><span class="sxs-lookup"><span data-stu-id="8974a-121">If Call Park application settings are different for the Skype for Business Server 2019 and legacy environments, use the cmdlet below as a template to update those changes.</span></span> 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

<span data-ttu-id="8974a-122">Para reatribuir todos os intervalos órbitas do estacionamento de chamadas do pool herdado ao pool do Skype for Business Server 2019, você pode usar o painel de controle do Skype for Business Server ou o Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8974a-122">To reassign all Call Park orbit ranges from the legacy pool to the Skype for Business Server 2019 pool, you can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a><span data-ttu-id="8974a-123">Reatribuir todas as faixas órbitas do estacionamento de chamadas usando o painel de controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8974a-123">Reassign all Call Park Orbit Ranges using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="8974a-124">Abra o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8974a-124">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="8974a-125">No painel esquerdo, selecione **recursos de voz**.</span><span class="sxs-lookup"><span data-stu-id="8974a-125">In the left pane, select **Voice Features**.</span></span>

3. <span data-ttu-id="8974a-126">Selecione a guia **estacionamento de chamadas** .</span><span class="sxs-lookup"><span data-stu-id="8974a-126">Select the **Call Park** tab.</span></span> 

4. <span data-ttu-id="8974a-127">Para cada intervalo de linha de plano de chamada atribuída a um pool herdado, edite a configuração do **FQDN do servidor de destino** e selecione o pool do Skype for Business Server 2019 que processará as solicitações de estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="8974a-127">For each Call Park orbit range assigned to a legacy pool, edit the **FQDN of destination server** setting and select the Skype for Business Server 2019 pool that will process the Call Park requests.</span></span> 

5. <span data-ttu-id="8974a-128">Selecione **confirmar** para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="8974a-128">Select **Commit** to save the changes.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a><span data-ttu-id="8974a-129">Reatribuir todas as faixas órbitas do estacionamento de chamadas usando o Shell de gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8974a-129">Reassign all Call Park Orbit Ranges using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="8974a-130">Abrir o Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8974a-130">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="8974a-131">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8974a-131">At the command line, type the following:</span></span>

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    <span data-ttu-id="8974a-132">Esse cmdlet lista todos os intervalos de o parque de chamadas órbitas na implantação.</span><span class="sxs-lookup"><span data-stu-id="8974a-132">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="8974a-133">Todas as órbitas do estacionamento de chamada com os parâmetros **CallParkServiceId** e **CallParkServerFqdn** definidas como o pool herdado devem ser reatribuídas.</span><span class="sxs-lookup"><span data-stu-id="8974a-133">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the legacy pool must be reassigned.</span></span> 

    <span data-ttu-id="8974a-134">Para reatribuir os intervalos de linha de chamada de barra de chamadas herdadas ao pool do Skype for Business Server 2019, na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8974a-134">To reassign the legacy Call Park orbit ranges to the Skype for Business Server 2019 pool, at the command line, type the following:</span></span>

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

<span data-ttu-id="8974a-135">Depois de reatribuir todos os intervalos de chamada de estacionamento de chamada ao pool do Skype for Business Server 2019, o processo de migração para o aplicativo de estacionamento de chamadas será concluído e o pool do Skype for Business Server 2019 cuidará de todas as solicitações de suporte ao parque do Skype.</span><span class="sxs-lookup"><span data-stu-id="8974a-135">After reassigning all Call Park orbit ranges to the Skype for Business Server 2019 pool, the migration process for the Call Park application will be completed and the Skype for Business Server 2019 pool will handle all future Call Park requests.</span></span>


