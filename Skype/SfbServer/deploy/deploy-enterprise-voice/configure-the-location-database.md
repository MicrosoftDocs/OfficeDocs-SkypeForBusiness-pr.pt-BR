---
title: Configurar o banco de dados de localização no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: Configurar, preencher e publicar o banco de dados de local E9-1-1 no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 5aad449d8d286fb4bd71373be33baea9cbb2c8f3
ms.sourcegitcommit: 5e6eb8286bd5eb318a901e42235e91a58946c3a9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2019
ms.locfileid: "38038700"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a><span data-ttu-id="9877a-103">Configurar o banco de dados de localização no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9877a-103">Configure the location database in Skype for Business Server</span></span>
 
<span data-ttu-id="9877a-104">Configurar, preencher e publicar o banco de dados de local E9-1-1 no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="9877a-104">Configure, populate, and publish the E9-1-1 location database in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="9877a-105">Para que os clientes possam detectar automaticamente seu local na rede, primeiro configure o banco de dados de localização.</span><span class="sxs-lookup"><span data-stu-id="9877a-105">To enable clients to automatically detect their location within a network, you first need to configure the location database.</span></span> 
  
<span data-ttu-id="9877a-106">Para configurar o banco de dados local, execute as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="9877a-106">To configure the location database, perform the following tasks:</span></span>
  
- <span data-ttu-id="9877a-107">Preencha o banco de dados com um mapeamento dos locais para os elementos de rede.</span><span class="sxs-lookup"><span data-stu-id="9877a-107">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="9877a-108">Se você usar um gateway de número de identificação de localização de emergência (ELIN), precisará incluir o \<Elin\> no campo CompanyName.</span><span class="sxs-lookup"><span data-stu-id="9877a-108">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>
    
    <span data-ttu-id="9877a-109">Se você não preencher o banco de dados local e o **Local necessário** na Política de Localização está definido para **Sim** ou **Isenção de Responsabilidade**, o cliente solicitará que o usuário insira um local manualmente.</span><span class="sxs-lookup"><span data-stu-id="9877a-109">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>
    
- <span data-ttu-id="9877a-110">Valide os endereços em relação ao MSAG (catálogo de endereços principal) mantido pelo provedor de serviços de emergência.</span><span class="sxs-lookup"><span data-stu-id="9877a-110">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>
    
- <span data-ttu-id="9877a-111">Publique o banco de dados atualizado.</span><span class="sxs-lookup"><span data-stu-id="9877a-111">Publish the updated database.</span></span>
    
## <a name="populate-the-location-database"></a><span data-ttu-id="9877a-112">Preencher o banco de dados de local</span><span class="sxs-lookup"><span data-stu-id="9877a-112">Populate the location database</span></span>

<span data-ttu-id="9877a-113">Para localizar clientes automaticamente em uma rede, primeiro você precisa preencher o banco de dados de localização com um mapa de conexões de rede, que mapeia os elementos de rede para endereços residenciais (ou seja, ruas).</span><span class="sxs-lookup"><span data-stu-id="9877a-113">To automatically locate clients within a network, you first need to populate the location database with a network wiremap, which maps network elements to civic (that is, street) addresses.</span></span> <span data-ttu-id="9877a-114">Você pode usar sub-redes, pontos de acesso sem fio, opções e portas para definir o mapa de conexões.</span><span class="sxs-lookup"><span data-stu-id="9877a-114">You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>
  
<span data-ttu-id="9877a-115">É possível adicionar endereços ao banco de dados local individualmente ou em massa usando um arquivo CSV contendo os formatos de coluna descritos na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="9877a-115">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>
  
<span data-ttu-id="9877a-p103">Se você usa um gateway de número da chamada de emergência (Emergency Location Identification Number - ELIN), inclua o ELIN no campo **CompanyName** para cada local. Você pode incluir diversos ELINs para cada local, separados por ponto e vírgula.</span><span class="sxs-lookup"><span data-stu-id="9877a-p103">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location. You can include multiple ELINs for each location, each separated by a semicolon.</span></span>
  
|<span data-ttu-id="9877a-118">**Elemento de rede**</span><span class="sxs-lookup"><span data-stu-id="9877a-118">**Network Element**</span></span>|<span data-ttu-id="9877a-119">**Colunas obrigatórias**</span><span class="sxs-lookup"><span data-stu-id="9877a-119">**Required Columns**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9877a-120">**Ponto de acesso sem fio**</span><span class="sxs-lookup"><span data-stu-id="9877a-120">**Wireless access point**</span></span> <br/> |<span data-ttu-id="9877a-121">\<BSSID\>,\<Descrição\>,\<local\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<predirectional\>,...</span><span class="sxs-lookup"><span data-stu-id="9877a-121">\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="9877a-122">... \<Streetname\>,\<StreetSuffix\>,\<monodirecional\>,\<cidade\>,\<estado\>,\<CEP\>,\<país\></span><span class="sxs-lookup"><span data-stu-id="9877a-122">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="9877a-123">**Sub-rede**</span><span class="sxs-lookup"><span data-stu-id="9877a-123">**Subnet**</span></span> <br/> |<span data-ttu-id="9877a-124">\<Sub-rede\>,\<Descrição\>,\<local\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<predirectional\>,...</span><span class="sxs-lookup"><span data-stu-id="9877a-124">\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="9877a-125">... \<Streetname\>,\<StreetSuffix\>,\<monodirecional\>,\<cidade\>,\<estado\>,\<CEP\>,\<país\></span><span class="sxs-lookup"><span data-stu-id="9877a-125">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="9877a-126">**Porta**</span><span class="sxs-lookup"><span data-stu-id="9877a-126">**Port**</span></span> <br/> |<span data-ttu-id="9877a-127">\<ChassisID\>,\<PortIDSubType\>,\<portid\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,...</span><span class="sxs-lookup"><span data-stu-id="9877a-127">\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,…</span></span>  <br/> <span data-ttu-id="9877a-128">... \<Predirectional\>,\<streetname\>,\<StreetSuffix\>,\<monodirecional\>,\<cidade\>,\<estado\>,\<CEP\>,\<país\></span><span class="sxs-lookup"><span data-stu-id="9877a-128">…\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="9877a-129">**Opção**</span><span class="sxs-lookup"><span data-stu-id="9877a-129">**Switch**</span></span> <br/> |<span data-ttu-id="9877a-130">\<ChassisID\>,\<Descrição\>,\<local\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<predirectional\>,...</span><span class="sxs-lookup"><span data-stu-id="9877a-130">\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="9877a-131">... \<Streetname\>,\<StreetSuffix\>,\<monodirecional\>,\<cidade\>,\<estado\>,\<CEP\>,\<país\></span><span class="sxs-lookup"><span data-stu-id="9877a-131">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="9877a-132">Para adicionar elementos de rede no banco de dados de localização</span><span class="sxs-lookup"><span data-stu-id="9877a-132">To add network elements to the location database</span></span>

1. <span data-ttu-id="9877a-133">Execute o seguinte cmdlet para adicionar um local de sub-rede ao banco de dados de localização.</span><span class="sxs-lookup"><span data-stu-id="9877a-133">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="9877a-p104">Para gateways de ELIN, informe o ELIN no campo CompanyName. Você pode incluir mais de um ELIN. Exemplo:</span><span class="sxs-lookup"><span data-stu-id="9877a-p104">For ELIN gateways, put the ELIN in the CompanyName field. You can include more than one ELIN. For example:</span></span>
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="9877a-137">Alternativamente, é possível executar os cmdlets a seguir e usar um arquivo denominado "subnets.csv" para atualização em massa de locais de sub-rede.</span><span class="sxs-lookup"><span data-stu-id="9877a-137">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
   ```
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. <span data-ttu-id="9877a-138">Execute o seguinte cmdlet para adicionar locais sem fio ao banco de dados de localização.</span><span class="sxs-lookup"><span data-stu-id="9877a-138">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
   ```
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="9877a-139">Alternativamente, é possível executar os cmdlets a seguir e usar um arquivo denominado "waps.csv" para atualização em massa de locais sem fio.</span><span class="sxs-lookup"><span data-stu-id="9877a-139">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
   ```
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. <span data-ttu-id="9877a-140">Execute o seguinte cmdlet para adicionar locais de opções ao banco de dados de localização.</span><span class="sxs-lookup"><span data-stu-id="9877a-140">Run the following cmdlet to add switch locations to the location database.</span></span>
    
   ```
   Set-CsLisSwitch -ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   <span data-ttu-id="9877a-141">Alternativamente, é possível executar os cmdlets a seguir e usar um arquivo denominado "switches.csv" para atualização em locais de switch.</span><span class="sxs-lookup"><span data-stu-id="9877a-141">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
   ```
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. <span data-ttu-id="9877a-142">Execute o seguinte cmdlet para adicionar locais de porta ao banco de dados de localização</span><span class="sxs-lookup"><span data-stu-id="9877a-142">Run the following cmdlet to add port locations to the location database</span></span>
    
   ```
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="9877a-p105">O padrão de PortIDSubType é LocallyAssigned. Você também pode definir para InterfaceAlias ou InterfaceName</span><span class="sxs-lookup"><span data-stu-id="9877a-p105">The default for PortIDSubType is LocallyAssigned. You can also set it to InterfaceAlias or InterfaceName</span></span>
    
   <span data-ttu-id="9877a-145">Alternativamente, é possível executar os cmdlets a seguir e usar um arquivo denominado "ports.csv" para atualização em massa de locais de porta.</span><span class="sxs-lookup"><span data-stu-id="9877a-145">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
   ```
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a><span data-ttu-id="9877a-146">Validar endereços</span><span class="sxs-lookup"><span data-stu-id="9877a-146">Validate addresses</span></span>

### <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="9877a-147">Para validar endereços localizados no banco de dados de localização</span><span class="sxs-lookup"><span data-stu-id="9877a-147">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="9877a-148">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="9877a-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="9877a-149">Execute os cmdlets a seguir para configurar a conexão com o provedor de serviços de emergência.</span><span class="sxs-lookup"><span data-stu-id="9877a-149">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
   ```
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. <span data-ttu-id="9877a-150">Execute o cmdlet a seguir para validar os endereços no banco de dados de localização.</span><span class="sxs-lookup"><span data-stu-id="9877a-150">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
   ```
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   <span data-ttu-id="9877a-151">Você também pode usar o cmdlet **Test-CsLisCivicAddress** para validar endereços individuais.</span><span class="sxs-lookup"><span data-stu-id="9877a-151">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>
    
## <a name="publish-the-location-database"></a><span data-ttu-id="9877a-152">Publicar o banco de dados de local</span><span class="sxs-lookup"><span data-stu-id="9877a-152">Publish the location database</span></span>

<span data-ttu-id="9877a-153">Os novos locais adicionados ao banco de dados de local não serão disponibilizados para o cliente até que sejam publicados.</span><span class="sxs-lookup"><span data-stu-id="9877a-153">The new locations that you added to the location database will not be made available to the client until they have been published.</span></span>
  
<span data-ttu-id="9877a-154">Se você usar gateways ELIN, também é necessário carregar os ELINs para o banco de dados ALI da transportadora PSTN.</span><span class="sxs-lookup"><span data-stu-id="9877a-154">If you use Emergency Location Identification Number (ELIN) gateways, you also need to upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span> <span data-ttu-id="9877a-155">Sua transportadora PSTN pode exigir que você use um formato específico para os registros ELIN.</span><span class="sxs-lookup"><span data-stu-id="9877a-155">Your PSTN carrier may require you to use a specific format for the ELIN records.</span></span> <span data-ttu-id="9877a-156">Entre em contato com sua transportadora PSTN para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="9877a-156">Contact your PSTN carrier for details.</span></span> <span data-ttu-id="9877a-157">Você pode exportar os registros do banco de dados do serviço de informações de localização e formatá-los conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="9877a-157">You can export the records from the Location Information service database and format them as required.</span></span>
  
### <a name="to-publish-the-location-database"></a><span data-ttu-id="9877a-158">Para publicar o banco de dados local</span><span class="sxs-lookup"><span data-stu-id="9877a-158">To publish the location database</span></span>

-  <span data-ttu-id="9877a-159">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="9877a-159">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
- <span data-ttu-id="9877a-160">Execute o seguinte cmdlet para publicar o banco de dados local.</span><span class="sxs-lookup"><span data-stu-id="9877a-160">Run the following cmdlet to publish the location database.</span></span>
    
  ```
  Publish-CsLisConfiguration
  ```


