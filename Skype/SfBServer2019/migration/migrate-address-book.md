---
title: Migrar catálogo de endereços
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
description: 'Em geral, o catálogo de endereços é migrado junto com o restante da sua topologia. No entanto, talvez seja necessário executar algumas etapas de migração após a personalização do seguinte em seu ambiente herdado:'
ms.openlocfilehash: 6d2ccf0d38814d149495518a71f888f0c2999d24
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752833"
---
# <a name="migrate-address-book"></a>Migrar o Catálogo de Endereços

Em geral, o catálogo de endereços é migrado junto com o restante da sua topologia. No entanto, talvez seja necessário executar algumas etapas de migração após a personalização do seguinte em seu ambiente herdado: 

- Personalizou as regras de normalização do Catálogo de Endereços

- Alterou o valor padrão do parâmetro **UseNormalizationRules** para Falso. 


 **Regras de Normalização do Catálogo de Endereços**

Se você personalizou as regras de normalização do catálogo de endereços no seu ambiente herdado, você deve migrar as regras personalizadas para o pool piloto. Se você não personalizou regras de normalização do Catálogo de Endereços, não há nada para migrar para o serviço do Catálogo de Endereços. As regras de normalização padrão para o Skype for Business Server 2019 são as mesmas regras padrão para a instalação herdada. Siga o procedimento posteriormente nesta seção para migrar regras de normalização personalizadas.

> [!NOTE]
> Se sua organização usa controle de chamadas remotas e você personalizou regras de normalização do Catálogo de Endereços, deve executar o procedimento deste tópico antes de usar o controle de chamadas remotas. O procedimento requer a associação no grupo RTCUniversalServerAdmins ou direitos equivalentes. 

 **UseNormalizationRules definido como Falso**

Se você definir o valor de **UseNormalizationRules** como false para que os usuários possam usar números de telefone como definidos nos serviços de domínio do Active Directory sem ter o Skype for Business Server 2019 aplicar regras de normalização, você precisará definir os parâmetros **UseNormalizationRules** e **IgnoreGenericRules** como true. Siga o procedimento posteriormente nesta seção para definir esses parâmetros como Verdadeiro. 

## <a name="to-migrate-address-book-customized-normalization-rules"></a>Para migrar regras de normalização personalizadas do Catálogo de Endereços

1. Localize o arquivo Company_Phone_Number_Normalization_Rules.txt na raiz da pasta compartilhada do catálogo de endereços e copie-o para a raiz da pasta compartilhada do catálogo de endereços em seu pool piloto do Skype for Business Server 2019.

    > [!NOTE]
    > The sample Address Book normalization rules have been installed in your ABS Web component file directory. O caminho é **$installedDriveLetter: \Arquivos de Programas\microsoft Skype for Business Server 2019 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**. Esse arquivo pode ser copiado e renomeado como **Company_Phone_Number_Normalization_Rules.txt** para o diretório raiz da pasta compartilhada do catálogo de endereços. Por exemplo, o catálogo de endereços compartilhado no **$serverX**, o caminho será semelhante a: ** \\ $serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**. 

2. Use um editor de texto, como o Bloco de Notas para abrir o arquivo Company_Phone_Number_Normalization_Rules.txt.

3. Determinados tipos de entradas não funcionarão corretamente no Skype for Business Server 2019. Pesquise no arquivo pelos tipos de entrada descritos nesta etapa,m edite-os conforme o necessário e salve as alterações na pasta compartilhada do Catálogo de Endereços em seu pool piloto.

    Cadeias de caracteres que incluem espaços em branco ou pontuações obrigatórios causam falha nas regras de normalização porque estes caracteres são excluídos da cadeia de caracteres que serve como entrada para as regras de normalização. Se você tem cadeias de caracteres que incluem espaços em branco ou pontuações obrigatórios, é necessário modificá-las. Por exemplo, a cadeia de caracteres a seguir causaria falha na regra de normalização:

   ```console
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    A cadeia de caracteres a seguir não causaria falha na regra de normalização:

   ```console
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>Para definir UseNormalizationRules e IgnoreGenericRules como verdadeiro

1. Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Skype for Business Server 2019**e em **Shell de gerenciamento do Skype for Business Server**.

2. Siga um destes procedimentos:

   - Se sua implantação incluir apenas o Skype for Business Server 2019, execute o seguinte cmdlet no nível global para alterar os valores de **UseNormalizationRules** e **IgnoreGenericRules** para true: 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - Se sua implantação incluir uma combinação do Skype for Business Server 2019 e uma instalação herdada, execute o cmdlet a seguir e atribua-a a cada pool do Skype for Business Server 2019 na topologia:

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. Aguarde a replicação do repositório de gerenciamento central ocorrer em todos os pools.

4. Modifique o arquivo de regras de normalização de telefone, "Company_Phone_Number_Normalization_Rules.txt", para sua implantação apagar o conteúdo. O arquivo está no compartilhamento de arquivos de cada pool do Skype for Business Server 2019. Se o arquivo não estiver presente, crie então um arquivo vazio chamado "Company_Phone_Number_Normalization_Rules.txt".

5. Aguarde alguns minutos para que todos os pools de front-ends leiam os novos arquivos.

6. Execute o cmdlet a seguir em cada pool do Skype for Business Server 2019 em sua implantação:

   ```PowerShell
   Update-CsAddressBook
   ```


