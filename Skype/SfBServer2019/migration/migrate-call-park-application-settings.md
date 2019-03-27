---
title: Migrar configurações do aplicativo do Estacionamento de Chamada
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'A migração do aplicativo inclui o Skype para Business Server 2019 pool com qualquer música personalizada em espera arquivos carregados na instalar herdado de provisionamento de estacionamento de chamada, restaurando as configurações de nível de serviço e redirecionando estacionamento de chamada todas as Órbitas para o Skype para Business Server 2019 pool. Se os arquivos de música de espera personalizados tiverem sido configurados no pool, esses arquivos precisam ser copiados para o novo Skype para Business Server 2019 pool. Além disso, é recomendável que você fazer backup de qualquer estacionamento de chamada personalizado arquivos de música de espera para outro destino para manter uma cópia de backup separada de qualquer música de espera arquivos personalizados que foram carregados para estacionamento de chamadas. Os arquivos de música de espera personalizados para o aplicativo de estacionamento de chamada são armazenados no armazenamento de arquivos do pool. Para copiar os arquivos de áudio de um repositório de arquivo do pool para um Skype para Business Server 2019 file store, use o comando Xcopiar com os seguintes parâmetros:'
ms.openlocfilehash: 3d9c2904d66ac5d35bdd94631ec23c67288a5c3a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887620"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="f713e-107">Migrar configurações do aplicativo do Estacionamento de Chamada</span><span class="sxs-lookup"><span data-stu-id="f713e-107">Migrate Call Park application settings</span></span>

<span data-ttu-id="f713e-108">A migração do aplicativo estacionamento de chamadas inclui o provisionamento do Skype para Business Server 2019 pool com quaisquer arquivos de música de espera personalizados que foram carregados na instalar herdado, restaurando as configurações de nível de serviço e o direcionamento novamente todas as Órbitas de estacionamento de chamada para o Skype para Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="f713e-108">The migration of the Call Park application includes provisioning the Skype for Business Server 2019 pool with any custom music-on-hold files that have been uploaded in the legacy install, restoring the service-level settings and re-targeting all Call Park orbits to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="f713e-109">Se os arquivos de música de espera personalizados tiverem sido configurados no pool, esses arquivos precisam ser copiados para o novo Skype para Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="f713e-109">If customized music-on-hold files have been configured in the pool, these files need to be copied to the new Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="f713e-110">Além disso, é recomendável que você fazer backup de qualquer estacionamento de chamada personalizado arquivos de música de espera para outro destino para manter uma cópia de backup separada de qualquer música de espera arquivos personalizados que foram carregados para estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="f713e-110">Additionally, it is recommended that you back up any Call Park customized music-on-hold files to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="f713e-111">Os arquivos de música de espera personalizados para o aplicativo de estacionamento de chamada são armazenados no armazenamento de arquivos do pool.</span><span class="sxs-lookup"><span data-stu-id="f713e-111">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="f713e-112">Para copiar os arquivos de áudio de um repositório de arquivo do pool para um Skype para Business Server 2019 file store, use o comando **Xcopiar** com os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="f713e-112">To copy the audio files from a pool file store to a Skype for Business Server 2019 file store, use the **Xcopy** command with the following parameters:</span></span> 

```
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

<span data-ttu-id="f713e-113">Quando todos os arquivos de áudio personalizados foram copiados para o Skype para Business Server 2019 file store, as configurações do aplicativo de estacionamento de chamada do Skype para o servidor de negócios 2019 pool deve ser configurado e estacionamento de chamada órbita intervalos que estão associados ao pool herdado devem ser reatribuídos para o Skype para Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="f713e-113">When all customized audio files have been copied to the Skype for Business Server 2019 file store, the Call Park application settings of the Skype for Business Server 2019 pool must be configured, and the Call Park orbit ranges that are associated with the legacy pool must be reassigned to the Skype for Business Server 2019 pool.</span></span>

<span data-ttu-id="f713e-114">As configurações do aplicativo de estacionamento de chamada incluem o limite de tempo limite de retirada, habilitando ou desabilitando a música em espera, as tentativas de retirada de máximo de chamadas e a solicitação de tempo limite.</span><span class="sxs-lookup"><span data-stu-id="f713e-114">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts, and the timeout request.</span></span> <span data-ttu-id="f713e-115">Você deve gerenciar configurações do aplicativo de estacionamento de chamada usando o Skype para Business Server Management Shell para executar o cmdlet **Set-CsCpsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="f713e-115">You must manage Call Park application settings by using the Skype for Business Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="f713e-116">Você não pode gerenciar as configurações do aplicativo de estacionamento de chamada usando o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="f713e-116">You cannot manage the Call Park application settings using the Skype for Business Server Control Panel.</span></span> 

## <a name="reconfigure-the-call-park-service-settings"></a><span data-ttu-id="f713e-117">Reconfigurar as definições do serviço de estacionamento de chamada</span><span class="sxs-lookup"><span data-stu-id="f713e-117">Reconfigure the Call Park Service Settings</span></span>

1. <span data-ttu-id="f713e-118">Em Skype para Business Server 2019 servidor Front-End, abra o Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="f713e-118">From the Skype for Business Server 2019 Front End Server, open the Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="f713e-119">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f713e-119">At the command line, type the following:</span></span>

    > [!NOTE]
    > <span data-ttu-id="f713e-120">Se seu Skype para configurações de aplicativo de negócios Server 2019 Call Park é idêntica às configurações herdadas, você poderá ignorar esta etapa.</span><span class="sxs-lookup"><span data-stu-id="f713e-120">If your Skype for Business Server 2019 Call Park application settings are identical to the legacy settings, you can skip this step.</span></span> <span data-ttu-id="f713e-121">Se as configurações do aplicativo de estacionamento de chamada são diferentes para o Skype para ambientes de legado e Business Server 2019, use o cmdlet abaixo como modelo para atualizar essas alterações.</span><span class="sxs-lookup"><span data-stu-id="f713e-121">If Call Park application settings are different for the Skype for Business Server 2019 and legacy environments, use the cmdlet below as a template to update those changes.</span></span> 

   ```
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

<span data-ttu-id="f713e-122">Para reatribuir todos os intervalos de órbita estacionamento de chamada do pool herdado para o Skype para Business Server 2019 pool, você pode usar o Skype para painel de controle do Business Server ou o Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="f713e-122">To reassign all Call Park orbit ranges from the legacy pool to the Skype for Business Server 2019 pool, you can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f713e-123">Reatribuir todos os intervalos de órbita de estacionamento de chamada usando o Skype para painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="f713e-123">Reassign all Call Park Orbit Ranges using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f713e-124">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="f713e-124">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="f713e-125">No painel esquerdo, selecione **Os recursos de voz**.</span><span class="sxs-lookup"><span data-stu-id="f713e-125">In the left pane, select **Voice Features**.</span></span>

3. <span data-ttu-id="f713e-126">Selecione a guia **Estacionamento de chamadas** .</span><span class="sxs-lookup"><span data-stu-id="f713e-126">Select the **Call Park** tab.</span></span> 

4. <span data-ttu-id="f713e-127">Para cada intervalo de órbita de estacionamento de chamadas atribuído a um pool herdado, edite a definição de **FQDN do servidor de destino** e selecione o Skype para pool de negócios Server 2019 que processará as solicitações do estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="f713e-127">For each Call Park orbit range assigned to a legacy pool, edit the **FQDN of destination server** setting and select the Skype for Business Server 2019 pool that will process the Call Park requests.</span></span> 

5. <span data-ttu-id="f713e-128">Selecione **Confirmar** para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="f713e-128">Select **Commit** to save the changes.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a><span data-ttu-id="f713e-129">Reatribuir todos os intervalos de órbita de estacionamento de chamada usando o Skype para Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="f713e-129">Reassign all Call Park Orbit Ranges using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="f713e-130">Abra o Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="f713e-130">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="f713e-131">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f713e-131">At the command line, type the following:</span></span>

   ```
   Get-CsCallParkOrbit
   ```

    <span data-ttu-id="f713e-132">Esse cmdlet lista todos os intervalos de órbita de estacionamento de chamada na implantação.</span><span class="sxs-lookup"><span data-stu-id="f713e-132">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="f713e-133">Todas as Órbitas de estacionamento de chamada com os parâmetros **CallParkServiceId** e **CallParkServerFqdn** definido como o pool herdado devem ser reatribuídas.</span><span class="sxs-lookup"><span data-stu-id="f713e-133">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the legacy pool must be reassigned.</span></span> 

    <span data-ttu-id="f713e-134">Para reatribuir a órbita de estacionamento de chamada herdada intervalos para o Skype para pool de negócios 2019 de servidor, na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f713e-134">To reassign the legacy Call Park orbit ranges to the Skype for Business Server 2019 pool, at the command line, type the following:</span></span>

   ```
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

<span data-ttu-id="f713e-135">Depois de reatribuir todos os intervalos de órbita de estacionamento de chamada para o Skype para Business Server 2019 pool, o processo de migração para o aplicativo de estacionamento de chamada será concluído e o Skype para Business Server 2019 pool lidará com todas as solicitações futuras de estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="f713e-135">After reassigning all Call Park orbit ranges to the Skype for Business Server 2019 pool, the migration process for the Call Park application will be completed and the Skype for Business Server 2019 pool will handle all future Call Park requests.</span></span>


