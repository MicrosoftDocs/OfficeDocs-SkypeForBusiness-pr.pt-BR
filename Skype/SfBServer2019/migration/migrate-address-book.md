---
title: Migrar o Catálogo de endereços
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Em geral, o catálogo de endereços é migrado juntamente com o restante da sua topologia. No entanto, talvez seja necessário executar algumas etapas de migração posterior se você tiver personalizado o seguinte em seu ambiente herdado:'
ms.openlocfilehash: 976717679a5a2f1dbdd1e2045cc5d5dfe43911e3
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888160"
---
# <a name="migrate-address-book"></a>Migrar o Catálogo de endereços

Em geral, o catálogo de endereços é migrado juntamente com o restante da sua topologia. No entanto, talvez seja necessário executar algumas etapas de migração posterior se você tiver personalizado o seguinte em seu ambiente herdado: 

- Personalizadas as regras de normalização do catálogo de endereços.

- Alterado o valor padrão para o parâmetro **UseNormalizationRules** para false. 


 **Regras de normalização de catálogo de endereços**

Se você personalizou as regras de normalização de catálogo de endereços em seu ambiente herdado, deve migrar as regras personalizadas para o pool piloto. Se você não tiver personalizado as regras de normalização de catálogo de endereços, não há nada para migrar para o serviço de catálogo de endereços. As regras de normalização padrão do Skype for Business Server 2019 são as mesmas regras padrão para a instalação herdada. Siga o procedimento mais adiante nesta seção para migrar regras de normalização personalizadas.

> [!NOTE]
> Se a sua organização usa o controle de chamada remota e você personalizou regras de normalização de catálogo de endereços, você deve executar o procedimento neste tópico antes de poder usar o controle de chamada remota. O procedimento requer associação no grupo RTCUniversalServerAdmins ou direitos equivalentes. 

 **UseNormalizationRules definido como false**

Se você definir o valor de **UseNormalizationRules** como false para que os usuários possam usar números de telefone conforme são definidos nos serviços de domínio Active Directory sem ter o Skype for Business Server 2019, aplique as regras de normalização, você precisa definir os parâmetros **UseNormalizationRules** e **IgnoreGenericRules** para true. Siga o procedimento mais adiante nesta seção para definir esses parâmetros como true. 

## <a name="to-migrate-address-book-customized-normalization-rules"></a>Para migrar regras de normalização personalizadas do catálogo de endereços

1. Localize o arquivo Company_Phone_Number_Normalization_Rules. txt na raiz da pasta compartilhada do catálogo de endereços e copie-o para a raiz da pasta compartilhada do catálogo de endereços no pool piloto do Skype for Business Server 2019.

    > [!NOTE]
    > O exemplo de regras de normalização de catálogo de endereços foi instalado no diretório de arquivos do componente da Web do ABS. O caminho é **$installedDriveLetter: \Arquivos de Programas\microsoft Skype for Business Server 2019 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules. txt**. Esse arquivo pode ser copiado e renomeado como **Company_Phone_Number_Normalization_Rules. txt** para o diretório raiz da pasta compartilhada do catálogo de endereços. Por exemplo, o catálogo de endereços compartilhado no **$serverX**, o caminho será semelhante a: ** \\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**. 

2. Use um editor de texto, como o bloco de notas, para abrir o arquivo Company_Phone_Number_Normalization_Rules. txt.

3. Certos tipos de entradas não funcionarão corretamente no Skype for Business Server 2019. Examine o arquivo para ver os tipos de entradas descritos nesta etapa, edite-os conforme necessário e salve as alterações na pasta compartilhada do catálogo de endereços em seu pool piloto.

    As cadeias de caracteres que incluem espaço em branco ou Pontuação necessários provocam falha nas regras de normalização porque esses caracteres são removidos da cadeia de caracteres que é inserida nas regras de normalização. Se você tiver cadeias de caracteres que incluam espaço em branco ou pontuação necessária, será necessário modificar as cadeias de caracteres. Por exemplo, a cadeia de caracteres a seguir causa falha na regra de normalização:

   ```console
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    A cadeia de caracteres a seguir não causaria falha na regra de normalização:

   ```console
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>Para definir UseNormalizationRules e IgnoreGenericRules como true

1. Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Skype for Business Server 2019**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**.

2. Siga um destes procedimentos:

   - Se sua implantação incluir somente o Skype for Business Server 2019, execute o seguinte cmdlet no nível global para alterar os valores de **UseNormalizationRules** e **IgnoreGenericRules** para true: 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - Se a sua implantação inclui uma combinação do Skype for Business Server 2019 e uma instalação herdada, execute o seguinte cmdlet e atribua-o a cada pool do Skype for Business Server 2019 na topologia:

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. Aguarde até que a replicação do repositório de gerenciamento central ocorra em todos os pools.

4. Modifique o arquivo de regras de normalização de telefone, "Company_Phone_Number_Normalization_Rules. txt", para sua implantação para limpar o conteúdo. O arquivo está no compartilhamento de arquivos de cada pool do Skype for Business Server 2019. Se o arquivo não estiver presente, crie um arquivo vazio chamado "Company_Phone_Number_Normalization_Rules. txt".

5. Aguarde alguns minutos para que todos os pools de front-end leiam os novos arquivos.

6. Execute o seguinte cmdlet em cada pool do Skype for Business Server 2019 na sua implantação:

   ```PowerShell
   Update-CsAddressBook
   ```


