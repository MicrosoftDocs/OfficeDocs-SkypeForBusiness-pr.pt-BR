---
title: Configurar o banco de dados de localização no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: Configurar, preencher e publicar o banco de dados de localização E9-1-1 no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 4c39ae7f3a73331c00a65a2fe364cb25d0010150
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-location-database-in-skype-for-business-server-2015"></a>Configurar o banco de dados de localização no Skype for Business Server 2015
 
Configurar, preencher e publicar o banco de dados de localização E9-1-1 no Skype para Business Server Enterprise Voice. 
  
Para que os clientes possam detectar automaticamente seu local na rede, primeiro configure o banco de dados de localização. 
  
Para configurar o banco de dados local, execute as seguintes tarefas:
  
- Preencha o banco de dados com um mapeamento dos locais para os elementos de rede. Se você usar um gateway ELIN Emergency Location Identification número (), você precisa incluir o ELIN no \<CompanyName\> campo.
    
    Se você não preencher o banco de dados local e o **Local necessário** na Política de Localização está definido para **Sim** ou **Isenção de Responsabilidade**, o cliente solicitará que o usuário insira um local manualmente.
    
- Valide os endereços em ao mestre endereço msag () mantido pelo provedor de serviços E9-1-1.
    
- Publique o banco de dados atualizado.
    
## <a name="populate-the-location-database"></a>Preencher o banco de dados de local

Para localizar automaticamente clientes dentro de uma rede, primeiro é preciso preencher o banco de dados de localização com um wiremap de rede, que mapeia os elementos de rede para residenciais (ou seja, rua) endereços. Você pode usar sub-redes, pontos de acesso sem fio, opções e portas para definir o mapa de conexões.
  
É possível adicionar endereços ao banco de dados local individualmente ou em massa usando um arquivo CSV contendo os formatos de coluna descritos na tabela a seguir.
  
Se você usa um gateway de número da chamada de emergência (Emergency Location Identification Number - ELIN), inclua o ELIN no campo **CompanyName** para cada local. Você pode incluir diversos ELINs para cada local, separados por ponto e vírgula.
  
|**Elemento da rede**|**Colunas obrigatórias**|
|:-----|:-----|
|**Ponto de acesso sem fio** <br/> |\<BSSID\>,\<descrição\>,\<local\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...  <br/> … \<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<estado\>,\<PostalCode\>,\<país\>  <br/> |
|**Sub-rede** <br/> |\<Subrede\>,\<descrição\>,\<local\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...  <br/> … \<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<estado\>,\<PostalCode\>,\<país\>  <br/> |
|**Porta** <br/> |\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<descrição\>,\<local\>,\<CompanyName\>,\<HouseNumber\>,\< HouseNumberSuffix\>,...  <br/> … \<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<estado\>,\<PostalCode\>,\< País\>  <br/> |
|**Opção** <br/> |\<ChassisID\>,\<descrição\>,\<local\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...  <br/> … \<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<estado\>,\<PostalCode\>,\<país\>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a>Para adicionar elementos de rede no banco de dados de localização

1. Execute o seguinte cmdlet para adicionar um local de sub-rede ao banco de dados de localização.
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    Para gateways de ELIN, informe o ELIN no campo CompanyName. Você pode incluir mais de um ELIN. Exemplo:
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    Alternativamente, é possível executar os cmdlets a seguir e usar um arquivo denominado "subnets.csv" para atualização em massa de locais de sub-rede.
    
   ```
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet

   ```

2. Execute o seguinte cmdlet para adicionar locais sem fio ao banco de dados de localização.
    
   ```
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   Alternativamente, é possível executar os cmdlets a seguir e usar um arquivo denominado "waps.csv" para atualização em massa de locais sem fio.
    
   ```
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. Execute o seguinte cmdlet para adicionar locais de opções ao banco de dados de localização.
    
   ```
   Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   Alternativamente, é possível executar os cmdlets a seguir e usar um arquivo denominado "switches.csv" para atualização em locais de switch.
    
   ```
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. Execute o seguinte cmdlet para adicionar locais de porta ao banco de dados de localização
    
   ```
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   O padrão de PortIDSubType é LocallyAssigned. Você também pode definir para InterfaceAlias ou InterfaceName
    
   Alternativamente, é possível executar os cmdlets a seguir e usar um arquivo denominado "ports.csv" para atualização em massa de locais de porta.
    
   ```
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a>Validar endereços

### <a name="to-validate-addresses-located-in-the-location-database"></a>Para validar endereços localizados no banco de dados de localização

1.  Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Execute os cmdlets a seguir para configurar a conexão com o provedor de serviços de emergência.
    
   ```
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

   ```

3. Execute o cmdlet a seguir para validar os endereços no banco de dados de localização.
    
   ```
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   Você também pode usar o cmdlet **Test-CsLisCivicAddress** para validar endereços individuais.
    
## <a name="publish-the-location-database"></a>Publicar o banco de dados de local

Os novos locais adicionados ao banco de dados de local não serão disponibilizados para o cliente até que sejam publicados.
  
Se você usar gateways ELIN, também é necessário carregar os ELINs para o banco de dados ALI da transportadora PSTN. Sua transportadora PSTN pode exigir que você use um formato específico para os registros ELIN. Entre em contato com sua transportadora PSTN para obter detalhes. Você pode exportar os registros do banco de dados de serviço de informações de local e formatá-los conforme necessário.
  
### <a name="to-publish-the-location-database"></a>Para publicar o banco de dados local

-  Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
- Execute o seguinte cmdlet para publicar o banco de dados local.
    
  ```
  Publish-CsLisConfiguration

  ```


