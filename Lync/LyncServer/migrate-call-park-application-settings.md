---
title: Migrar configurações do aplicativo do Estacionamento de Chamada
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f63b91c6a742310d14031bdadc28cbc6ca57e115
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503558"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="8db35-102">Migrar configurações do aplicativo do Estacionamento de Chamada</span><span class="sxs-lookup"><span data-stu-id="8db35-102">Migrate Call Park application settings</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8db35-103">_**Última modificação do tópico:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="8db35-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="8db35-104">A migração do aplicativo de estacionamento de chamada do Lync Server 2010 para o Lync Server 2013 inclui o provisionamento do pool do Lync Server 2013 com qualquer música personalizada em arquivos de espera que foram carregados no Lync Server 2010, restaurando as configurações de nível de serviço e redirecionando todas as órbitas de estacionamento de chamadas para o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8db35-104">The migration of the Call Park application from Lync Server 2010 to Lync Server 2013 includes provisioning the Lync Server 2013 pool with any custom music on hold files that have been uploaded in Lync Server 2010, restoring the service level settings and retargeting all Call Park orbits to the Lync Server 2013 pool.</span></span> <span data-ttu-id="8db35-105">Se os arquivos de música em espera personalizados tiverem sido configurados no pool do Lync Server 2010, esses arquivos precisam ser copiados para o novo pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8db35-105">If customized music-on-hold files have been configured in the Lync Server 2010 pool, these files need to be copied to the new Lync Server 2013 pool.</span></span> <span data-ttu-id="8db35-106">Além disso, é recomendável que você faça o backup de todos os arquivos de música em espera personalizados de um estacionamento de chamadas do Lync Server 2010 para outro destino, para manter uma cópia de backup separada de qualquer arquivo de música em espera personalizado que tenha sido carregado para estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="8db35-106">Additionally, it is recommended that you back up any Call Park customized music-on-hold files from Lync Server 2010 to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="8db35-107">Os arquivos de música em espera personalizados para o aplicativo de estacionamento de chamada são armazenados no repositório de arquivos do pool.</span><span class="sxs-lookup"><span data-stu-id="8db35-107">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="8db35-108">Para copiar os arquivos de áudio de um repositório de arquivos do pool do Lync Server 2010 para um repositório de arquivos do Lync Server 2013, use o comando **xcopy** com os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="8db35-108">To copy the audio files from a Lync Server 2010 pool file store to a Lync Server 2013 file store, use the **Xcopy** command with the following parameters:</span></span>

   ```console
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```console
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

<span data-ttu-id="8db35-109">Quando todos os arquivos de áudio personalizados foram copiados para o repositório de arquivos do Lync Server 2013, as configurações de aplicativo de estacionamento de chamada do pool do Lync Server 2013 devem ser configuradas, e os intervalos de órbita de estacionamento de chamada associados ao pool 2010 do Lync Server devem ser reatribuídos ao pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8db35-109">When all customized audio files have been copied to the Lync Server 2013 file store, the Call Park application settings of the Lync Server 2013 pool must be configured, and the Call Park orbit ranges that are associated with the Lync Server 2010 pool must be reassigned to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="8db35-110">As configurações do aplicativo de estacionamento de chamada incluem o limite de tempo limite de recebimento, habilitando ou desabilitando música em espera, o máximo de tentativas de recebimento de chamadas e a solicitação de tempo limite.</span><span class="sxs-lookup"><span data-stu-id="8db35-110">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts and the timeout request.</span></span> <span data-ttu-id="8db35-111">Você deve gerenciar as configurações do aplicativo de estacionamento de chamadas usando o Shell de gerenciamento do Lync Server para executar o cmdlet **set-CsCpsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="8db35-111">You must manage Call Park application settings by using the Lync Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="8db35-112">Você não pode gerenciar as configurações do aplicativo de estacionamento de chamada usando o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8db35-112">You cannot manage the Call Park application settings using the Lync Server Control Panel.</span></span>

<span data-ttu-id="8db35-113">**Reconfigurar as definições do serviço de estacionamento de chamadas**</span><span class="sxs-lookup"><span data-stu-id="8db35-113">**Reconfigure the Call Park Service Settings**</span></span>

1.  <span data-ttu-id="8db35-114">No servidor front-end do Lync Server 2013, abra o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8db35-114">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="8db35-115">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8db35-115">At the command line, type the following:</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8db35-116">Se as configurações do aplicativo de estacionamento de chamada do Lync Server 2013 forem idênticas às configurações herdadas do Lync Server 2010, você poderá ignorar a execução desta etapa.</span><span class="sxs-lookup"><span data-stu-id="8db35-116">If your Lync Server 2013 Call Park application settings are identical to the legacy Lync Server 2010 settings, you can skip running this step.</span></span> <span data-ttu-id="8db35-117">Se as configurações do aplicativo de estacionamento de chamada forem diferentes para os ambientes do Lync Server 2013 e do Lync Server 2010, use o cmdlet abaixo como um modelo para atualizar essas alterações.</span><span class="sxs-lookup"><span data-stu-id="8db35-117">If Call Park application settings are different for the Lync Server 2013 and Lync Server 2010 environments, use the cmdlet below as a template to update those changes.</span></span>

    
    <span data-ttu-id="8db35-118"></div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>"-CallPickupTimeoutThreshold" <LS2010 CPS TimeSpan> "-EnableMusicOnHold" <LS2010 CPS value> "-MaxCallPickupAttempts" <LS2010 CPS pickup attempts> "-OnTimeoutURI" <LS2010 CPS timeout URI> " ```</span><span class="sxs-lookup"><span data-stu-id="8db35-118"></div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>" ```</span></span>

<span data-ttu-id="8db35-119">Para reatribuir todos os intervalos de órbita de estacionamento de chamadas do pool do Lync Server 2010 ao pool do Lync Server 2013, você pode usar o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8db35-119">To reassign all Call Park orbit ranges from Lync Server 2010 pool to the Lync Server 2013 pool, you can use either the Lync Server Control Panel or the Lync Server Management Shell.</span></span>

<span data-ttu-id="8db35-120">**Reatribuir todos os intervalos de órbita de estacionamento de chamada usando o painel de controle do Lync Server**</span><span class="sxs-lookup"><span data-stu-id="8db35-120">**Reassign all Call Park Orbit Ranges using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="8db35-121">Abra o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8db35-121">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="8db35-122">No painel esquerdo, selecione **recursos de voz**.</span><span class="sxs-lookup"><span data-stu-id="8db35-122">In the left pane, select **Voice Features**.</span></span>

3.  <span data-ttu-id="8db35-123">Selecione a guia **estacionamento de chamada** .</span><span class="sxs-lookup"><span data-stu-id="8db35-123">Select the **Call Park** tab.</span></span>

4.  <span data-ttu-id="8db35-124">Para cada intervalo de órbita de estacionamento de chamada atribuído a um pool do Lync Server 2010, edite o **FQDN da configuração do servidor de destino** e selecione o pool do lync Server 2013 que processará as solicitações de estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="8db35-124">For each Call Park orbit range assigned to a Lync Server 2010 pool, edit the **FQDN of destination server** setting and select the Lync Server 2013 pool that will process the Call Park requests.</span></span>

5.  <span data-ttu-id="8db35-125">Selecione **confirmar** para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="8db35-125">Select **Commit** to save the changes.</span></span>

<span data-ttu-id="8db35-126">**Reatribuir todos os intervalos de órbita de estacionamento de chamadas usando o Shell de gerenciamento do Lync Server**</span><span class="sxs-lookup"><span data-stu-id="8db35-126">**Reassign all Call Park Orbit Ranges using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="8db35-127">Abra o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8db35-127">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="8db35-128">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8db35-128">At the command line, type the following:</span></span>
    ```powershell
    Get-CsCallParkOrbit
    ```
    
    <span data-ttu-id="8db35-129">Este cmdlet lista todos os intervalos de órbita de estacionamento de chamada na implantação.</span><span class="sxs-lookup"><span data-stu-id="8db35-129">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="8db35-130">Todas as órbitas de estacionamento de chamadas com os parâmetros **CallParkServiceId** e **CallParkServerFqdn** definidos como o pool do Lync Server 2010 devem ser reatribuídas.</span><span class="sxs-lookup"><span data-stu-id="8db35-130">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the Lync Server 2010 pool must be reassigned.</span></span>
    
    <span data-ttu-id="8db35-131">Para reatribuir os intervalos de órbita do estacionamento de chamadas do Lync Server 2010 ao pool do Lync Server 2013, na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8db35-131">To reassign the Lync Server 2010 Call Park orbit ranges to the Lync Server 2013 pool, at the command line, type the following:</span></span>
    
    ```powershell
    Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"
    ```

<span data-ttu-id="8db35-132">Após reatribuir todos os intervalos de órbita de estacionamento de chamadas para o pool do Lync Server 2013, o processo de migração para o aplicativo de estacionamento de chamada será concluído e o pool do Lync Server 2013 tratará de todas as solicitações de estacionamento de chamadas futuras.</span><span class="sxs-lookup"><span data-stu-id="8db35-132">After reassigning all Call Park orbit ranges to the Lync Server 2013 pool, the migration process for the Call Park application will be completed and the Lync Server 2013 pool will handle all future Call Park requests.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

