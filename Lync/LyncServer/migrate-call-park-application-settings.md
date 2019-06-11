---
title: Migrar configurações do aplicativo do Estacionamento de Chamada
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f01429a85b679ae5d3710585db84c17e6e64e34b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844271"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="eadc1-102">Migrar configurações do aplicativo do Estacionamento de Chamada</span><span class="sxs-lookup"><span data-stu-id="eadc1-102">Migrate Call Park application settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eadc1-103">_**Tópico da última modificação:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="eadc1-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="eadc1-104">A migração do aplicativo de estacionamento de chamada do Lync Server 2010 para o Lync Server 2013 inclui a configuração do pool do Lync Server 2013 com qualquer música personalizada em arquivos de retenção que foram carregados no Lync Server 2010, a restauração das configurações de nível de serviço e o redirecionamento todas as órbitas de estacionamento de chamadas para o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eadc1-104">The migration of the Call Park application from Lync Server 2010 to Lync Server 2013 includes provisioning the Lync Server 2013 pool with any custom music on hold files that have been uploaded in Lync Server 2010, restoring the service level settings and retargeting all Call Park orbits to the Lync Server 2013 pool.</span></span> <span data-ttu-id="eadc1-105">Se os arquivos de música em espera personalizados tiverem sido configurados no pool do Lync Server 2010, esses arquivos precisarão ser copiados para o novo pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eadc1-105">If customized music-on-hold files have been configured in the Lync Server 2010 pool, these files need to be copied to the new Lync Server 2013 pool.</span></span> <span data-ttu-id="eadc1-106">Além disso, é recomendável que você faça o backup de todos os arquivos de música em espera personalizados do Lync Server 2010 para outro destino para manter uma cópia de backup separada de qualquer arquivo de música em espera personalizado que tenha sido carregado para o parque da chamada.</span><span class="sxs-lookup"><span data-stu-id="eadc1-106">Additionally, it is recommended that you back up any Call Park customized music-on-hold files from Lync Server 2010 to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="eadc1-107">Os arquivos de música em espera personalizados para o aplicativo de estacionamento de chamadas são armazenados no repositório de arquivos do pool.</span><span class="sxs-lookup"><span data-stu-id="eadc1-107">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="eadc1-108">Para copiar os arquivos de áudio de um repositório de arquivos de pool do Lync Server 2010 para um repositório de arquivos do Lync Server 2013, use o comando **xcopy** com os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="eadc1-108">To copy the audio files from a Lync Server 2010 pool file store to a Lync Server 2013 file store, use the **Xcopy** command with the following parameters:</span></span>

   ```
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

<span data-ttu-id="eadc1-109">Quando todos os arquivos de áudio personalizados foram copiados para o repositório de arquivos do Lync Server 2013, as configurações do aplicativo de estacionamento de chamada do pool do Lync Server 2013 devem ser configuradas, e as faixas órbitas do estacionamento de chamada associadas ao pool do Lync Server 2010 devem ser reatribuídas a o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eadc1-109">When all customized audio files have been copied to the Lync Server 2013 file store, the Call Park application settings of the Lync Server 2013 pool must be configured, and the Call Park orbit ranges that are associated with the Lync Server 2010 pool must be reassigned to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="eadc1-110">As configurações do aplicativo de estacionamento de chamada incluem o limite de tempo limite de separação, habilitando ou desabilitando música em espera, o número máximo de tentativas de chamadas e a solicitação de tempo limite.</span><span class="sxs-lookup"><span data-stu-id="eadc1-110">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts and the timeout request.</span></span> <span data-ttu-id="eadc1-111">Você deve gerenciar as configurações do aplicativo parque de chamadas usando o Shell de gerenciamento do Lync Server para executar o cmdlet **set-CsCpsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="eadc1-111">You must manage Call Park application settings by using the Lync Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="eadc1-112">Não é possível gerenciar as configurações do aplicativo parque de chamadas usando o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eadc1-112">You cannot manage the Call Park application settings using the Lync Server Control Panel.</span></span>

<span data-ttu-id="eadc1-113">**Reconfigurar as configurações de serviço do estacionamento de chamada**</span><span class="sxs-lookup"><span data-stu-id="eadc1-113">**Reconfigure the Call Park Service Settings**</span></span>

1.  <span data-ttu-id="eadc1-114">No servidor de front-end do Lync Server 2013, abra o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eadc1-114">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="eadc1-115">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="eadc1-115">At the command line, type the following:</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eadc1-116">Se as configurações do aplicativo do Lync Server 2013 Call Park forem idênticas às configurações herdadas do Lync Server 2010, você poderá ignorar a execução desta etapa.</span><span class="sxs-lookup"><span data-stu-id="eadc1-116">If your Lync Server 2013 Call Park application settings are identical to the legacy Lync Server 2010 settings, you can skip running this step.</span></span> <span data-ttu-id="eadc1-117">Se as configurações do aplicativo de estacionamento de chamada forem diferentes para os ambientes Lync Server 2013 e Lync Server 2010, use o cmdlet abaixo como um modelo para atualizar essas alterações.</span><span class="sxs-lookup"><span data-stu-id="eadc1-117">If Call Park application settings are different for the Lync Server 2013 and Lync Server 2010 environments, use the cmdlet below as a template to update those changes.</span></span>

    
    </div>
    
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"

<span data-ttu-id="eadc1-118">Para reatribuir todos os intervalos órbitas do parque de chamadas do pool do Lync Server 2010 ao pool do Lync Server 2013, você pode usar o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eadc1-118">To reassign all Call Park orbit ranges from Lync Server 2010 pool to the Lync Server 2013 pool, you can use either the Lync Server Control Panel or the Lync Server Management Shell.</span></span>

<span data-ttu-id="eadc1-119">**Reatribuir todas as faixas órbitas do estacionamento de chamada usando o painel de controle do Lync Server**</span><span class="sxs-lookup"><span data-stu-id="eadc1-119">**Reassign all Call Park Orbit Ranges using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="eadc1-120">Abra o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eadc1-120">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="eadc1-121">No painel esquerdo, selecione **recursos de voz**.</span><span class="sxs-lookup"><span data-stu-id="eadc1-121">In the left pane, select **Voice Features**.</span></span>

3.  <span data-ttu-id="eadc1-122">Selecione a guia **estacionamento de chamadas** .</span><span class="sxs-lookup"><span data-stu-id="eadc1-122">Select the **Call Park** tab.</span></span>

4.  <span data-ttu-id="eadc1-123">Para cada intervalo de linha de plano de chamada atribuída a um pool do Lync Server 2010, edite a configuração **FQDN do servidor de destino** e selecione o pool do lync Server 2013 que processará as solicitações do parque de chamadas.</span><span class="sxs-lookup"><span data-stu-id="eadc1-123">For each Call Park orbit range assigned to a Lync Server 2010 pool, edit the **FQDN of destination server** setting and select the Lync Server 2013 pool that will process the Call Park requests.</span></span>

5.  <span data-ttu-id="eadc1-124">Selecione **confirmar** para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="eadc1-124">Select **Commit** to save the changes.</span></span>

<span data-ttu-id="eadc1-125">**Reatribuir todas as faixas órbitas do estacionamento de chamadas usando o Shell de gerenciamento do Lync Server**</span><span class="sxs-lookup"><span data-stu-id="eadc1-125">**Reassign all Call Park Orbit Ranges using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="eadc1-126">Abra o Shell de Gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eadc1-126">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="eadc1-127">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="eadc1-127">At the command line, type the following:</span></span>
    
        Get-CsCallParkOrbit
    
    <span data-ttu-id="eadc1-128">Esse cmdlet lista todos os intervalos de o parque de chamadas órbitas na implantação.</span><span class="sxs-lookup"><span data-stu-id="eadc1-128">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="eadc1-129">Todas as órbitas do estacionamento de chamada com os parâmetros **CallParkServiceId** e **CallParkServerFqdn** definidas como o pool do Lync Server 2010 devem ser reatribuídas.</span><span class="sxs-lookup"><span data-stu-id="eadc1-129">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the Lync Server 2010 pool must be reassigned.</span></span>
    
    <span data-ttu-id="eadc1-130">Para reatribuir os intervalos de o parque de chamadas do Lync Server 2010 ao Lync Server 2013, na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="eadc1-130">To reassign the Lync Server 2010 Call Park orbit ranges to the Lync Server 2013 pool, at the command line, type the following:</span></span>
    
        Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"

<span data-ttu-id="eadc1-131">Depois de reatribuir todos os intervalos de chamadas de estacionamento de chamada para o pool do Lync Server 2013, o processo de migração para o aplicativo de estacionamento de chamada será concluído e o pool do Lync Server 2013 atenderá a todas as solicitações de suporte ao parque do futuro.</span><span class="sxs-lookup"><span data-stu-id="eadc1-131">After reassigning all Call Park orbit ranges to the Lync Server 2013 pool, the migration process for the Call Park application will be completed and the Lync Server 2013 pool will handle all future Call Park requests.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

