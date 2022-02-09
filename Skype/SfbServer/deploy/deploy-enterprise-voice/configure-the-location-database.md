---
title: Configurar o banco de dados de localização em Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: Configure, preencha e publique o banco de dados de localização E9-1-1 no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 5ebace7eabe0db04f06611bc9c11263021733367
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62400715"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a>Configurar o banco de dados de localização em Skype for Business Server
 
Configure, preencha e publique o banco de dados de localização E9-1-1 no Skype for Business Server Enterprise Voice. 
  
Para que os clientes possam detectar automaticamente seu local na rede, primeiro configure o banco de dados de localização. 
  
Para configurar o banco de dados de localização, execute as seguintes tarefas:
  
- Preencha o banco de dados com um mapeamento de elementos de rede para os locais. Se você usar um gateway ELIN (Número de Identificação de Local de Emergência), você precisará incluir o ELIN no \<CompanyName\> campo.
    
    Se você não preencher o banco de dados local e o **Local necessário** na Política de Localização está definido para **Sim** ou **Isenção de Responsabilidade**, o cliente solicitará que o usuário insira um local manualmente.
    
- Valide os endereços em relação ao MSAG (catálogo de endereços principal) mantido pelo provedor de serviços de emergência.
    
- Publicar o banco de dados atualizado.
    
## <a name="populate-the-location-database"></a>Preencher o banco de dados de localização

Para localizar clientes automaticamente em uma rede, primeiro você precisa preencher o banco de dados de localização com um mapa de conexões de rede, que mapeia os elementos de rede para endereços residenciais (ou seja, ruas). Você pode usar subredes, pontos de acesso sem fio, opções e portas para definir o mapa de conexões.
  
É possível adicionar endereços ao banco de dados local individualmente ou em massa usando um arquivo CSV contendo os formatos de coluna descritos na tabela a seguir.
  
Se você usa um gateway de número da chamada de emergência (Emergency Location Identification Number - ELIN), inclua o ELIN no campo **CompanyName** para cada local. Você pode incluir diversos ELINs para cada local, separados por ponto e vírgula.
  
|**Elemento de rede**|**Colunas obrigatórias**|
|:-----|:-----|
|**Ponto de acesso sem fio** <br/> |\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…  <br/> …\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**Sub-rede** <br/> |\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…  <br/> …\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**Porta** <br/> |\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,…  <br/> …\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**Switch** <br/> |\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…  <br/> …\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a>Para adicionar elementos de rede no banco de dados de localização

1. Execute o seguinte cmdlet para adicionar um local de subrede ao banco de dados de localização.
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    Para gateways de ELIN, informe o ELIN no campo CompanyName. Você pode incluir mais de um ELIN. Exemplo:
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    Alternativamente, é possível executar os cmdlets a seguir e usar um arquivo denominado "subnets.csv" para atualização em massa de locais de subrede.
    
   ```powershell
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. Execute o seguinte cmdlet para adicionar locais sem fio ao banco de dados de localização.
    
   ```powershell
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   Alternativamente, é possível executar os cmdlets a seguir e usar um arquivo denominado "waps.csv" para atualização em massa de locais sem fio.
    
   ```powershell
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. Execute o seguinte cmdlet para adicionar locais de opções ao banco de dados de localização.
    
   ```powershell
   Set-CsLisSwitch -ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   Alternativamente, é possível executar os cmdlets a seguir e usar um arquivo denominado "switches.csv" para atualização em locais de switch.
    
   ```powershell
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. Execute o seguinte cmdlet para adicionar locais de porta ao banco de dados de localização
    
   ```powershell
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   O padrão de PortIDSubType é LocallyAssigned. Você também pode definir para InterfaceAlias ou InterfaceName
    
   Alternativamente, é possível executar os cmdlets a seguir e usar um arquivo denominado "ports.csv" para atualização em massa de locais de porta.
    
   ```powershell
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a>Validar endereços

### <a name="to-validate-addresses-located-in-the-location-database"></a>Para validar endereços localizados no banco de dados de localização

1.  Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, em** Todos os **Programas, em** Skype for Business **2015** e em Skype for Business Server **Gerenciamento**.
    
2. Execute os cmdlets a seguir para configurar a conexão com o provedor de serviços de emergência.
    
   ```powershell
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. Execute o cmdlet a seguir para validar os endereços no banco de dados de localização.
    
   ```powershell
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   Você também pode usar o cmdlet **Test-CsLisCivicAddress** para validar endereços individuais.
    
## <a name="publish-the-location-database"></a>Publicar o banco de dados de localização

Os novos locais adicionados ao banco de dados de localização não serão disponibilizados para o cliente até que sejam publicados.
  
Se você usar gateways ELIN (Número de Identificação de Local de Emergência), também precisará carregar os ELINs para o banco de dados de Identificação Automática de Localização (ALI) da operadora PSTN (rede telefônica pública comutado). Sua operadora PSTN pode exigir que você use um formato específico para os registros ELIN. Entre em contato com sua operadora PSTN para obter detalhes. Você pode exportar os registros do banco de dados do serviço Informações de Local e formatar-os conforme necessário.
  
### <a name="to-publish-the-location-database"></a>Para publicar o banco de dados de localização

-  Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, em** Todos os **Programas, em** Skype for Business **2015** e em Skype for Business Server **Gerenciamento**.
    
- Execute o cmdlet a seguir para publicar o banco de dados de localização.
    
  ```powershell
  Publish-CsLisConfiguration
  ```


