---
title: Migrar catálogo de endereços
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Em geral, o catálogo de endereços é migrado com o restante de sua topologia. No entanto, você talvez precise executar algumas etapas de pós-migração se você personalizou o seguinte no seu ambiente Herdado:'
ms.openlocfilehash: 14c9194b8c32ab5db64096c2aa3308a31812c6f8
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030466"
---
# <a name="migrate-address-book"></a>Migrar catálogo de endereços

Em geral, o catálogo de endereços é migrado com o restante de sua topologia. No entanto, você talvez precise executar algumas etapas de pós-migração se você personalizou o seguinte no seu ambiente Herdado: 
  
- Defina a propriedade de WMI **PartitionbyOU** para agrupar entradas do catálogo de endereços por unidade organizacional (UO). 
    
- Personalizou as regras de normalização do catálogo de endereços.
    
- Alterado o valor padrão do parâmetro **UseNormalizationRules** para falso. 
    
 **Entradas do catálogo de endereços agrupadas**
  
Se você definir a propriedade WMI **PartitionbyOU** como True para criar catálogos de endereços para cada unidade Organizacional, você precisará definir o atributo **msRTCSIP-GroupingId** do Active Directory em usuários e contatos se você quiser continuar agrupar entradas do catálogo de endereços. Convém para agrupar entradas do catálogo de endereços para limitar o escopo das pesquisas de catálogo de endereços. Para usar o atributo **msRTCSIP-GroupingId** , escreva um script para preencher o atributo, atribuindo o mesmo valor para todos os usuários que você deseja agrupar. Por exemplo, atribua um valor único para todos os usuários em uma unidade Organizacional. 
  
 **Regras de normalização do catálogo de endereços**
  
Se você personalizou regras de normalização do catálogo de endereços em seu ambiente herdado, você deve migrar as regras personalizadas para seu pool piloto. Se você não personalizar regras de normalização do catálogo de endereços, você não tem nada para migrar para o serviço de catálogo de endereços. As regras de normalização padrão para Skype para Business Server 2019 são os mesmos as regras padrão para a instalação de legado. Siga o procedimento nesta seção para migrar regras de normalização personalizada.
  
> [!NOTE]
> Se sua organização usa controle de chamada remota e você personalizou regras de normalização do catálogo de endereços, você deve executar o procedimento neste tópico antes de poder usar o controle de chamada remota. O procedimento requer a participação no grupo RTCUniversalServerAdmins ou direitos equivalentes. 
  
 **UseNormalizationRules definido como falso**
  
Se definir o valor de **UseNormalizationRules** como False para que os usuários possam usar números de telefone como eles são definidos no Active Directory Domain Services sem ter que Skype para Business Server 2019 aplicar regras de normalização, você precisará definir o ** UseNormalizationRules** e os parâmetros de **IgnoreGenericRules** como True. Siga o procedimento nesta seção para definir esses parâmetros como True. 
  
## <a name="to-migrate-address-book-customized-normalization-rules"></a>Para migrar o catálogo de endereços personalizou regras de normalização

1. Encontre o arquivo company_phone_number_normalization_rules txt na raiz da pasta compartilhada do catálogo de endereços e copie-o para a raiz da pasta compartilhada do catálogo de endereços em seu Skype para o pool piloto Business Server 2019.
    
    > [!NOTE]
    > As regras de normalização do catálogo de endereços de amostra tenham sido instaladas no seu diretório de arquivo do componente Web ABS. O caminho é **$installedDriveLetter: \Program Files\Microsoft Skype para Business Server 2019\Web Components\Address catálogo Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**. Esse arquivo possa ser copiado e renomeado como **company_phone_number_normalization_rules** para o diretório raiz do endereço catálogo compartilhado da pasta. Por exemplo, o catálogo de endereços compartilhado em **$serverX**, o caminho será semelhante a: ** \\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**. 
  
2. Use um editor de texto, como o bloco de notas, para abrir o arquivo company_phone_number_normalization_rules txt.
    
3. Certos tipos de entradas não funcionará corretamente no Skype para Business Server 2019. Examine o arquivo para os tipos de entradas descritos nesta etapa, editá-los conforme o necessário e salvar as alterações para a pasta compartilhada do catálogo de endereços em seu pool piloto.
    
    Cadeias de caracteres que incluem necessárias de espaço em branco ou pontuação causa regras de normalização falhe, pois esses caracteres são removidos sem a cadeia de caracteres que é de entrada para as regras de normalização. Se você tiver as cadeias de caracteres que incluem necessário de espaço em branco ou pontuação, você precisará modificar as cadeias de caracteres. Por exemplo, a seguinte sequência causaria Falha na regra de normalização:
    
  ```
  \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
  ```

    A cadeia de caracteres a seguir não causaria Falha na regra de normalização:
    
  ```
  \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
  ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>Para definir UseNormalizationRules e IgnoreGenericRules como true

1. Inicie o Skype do Shell de gerenciamento do servidor de negócios: clique em **Iniciar**, clique em **Todos os programas**, clique em **Microsoft Skype para Business Server 2019**e, em seguida, clique em **Skype do Shell de gerenciamento do servidor de negócios**.
    
2. Use uma das seguintes opções:
    
  - Se sua implantação incluir apenas Skype para Business Server 2019, execute o seguinte cmdlet em nível global para alterar os valores de **UseNormalizationRules** e **IgnoreGenericRules** para verdadeiro: 
    
  ```
  Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
  
  ```

  - Se sua implantação incluir uma combinação de Skype para Business Server 2019 e uma instalação herdada, execute o seguinte cmdlet e atribuí-lo a cada Skype para Business Server 2019 pool na topologia:
    
  ```
  New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
  
  ```

3. Aguarde a replicação do repositório de gerenciamento Central ocorra em todos os pools.
    
4. Modifica o arquivo de regras de normalização de telefone, "Company_phone_number_normalization_rules", para sua implantação limpar o conteúdo. O arquivo está no compartilhamento de arquivos de cada Skype para Business Server 2019 pool. Se o arquivo não estiver presente, em seguida, crie um arquivo vazio chamado "Company_phone_number_normalization_rules".
    
5. Espere alguns minutos para todos os pools de Front-End ler os novos arquivos.
    
6. Execute o seguinte cmdlet em cada Skype para Business Server 2019 pool em sua implantação:
    
  ```
  Update-CsAddressBook
  
  ```


