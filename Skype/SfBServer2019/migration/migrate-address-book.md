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
ms.localizationpriority: medium
description: 'Em geral, o Livro de Endereços é migrado juntamente com o restante de sua topologia. No entanto, talvez seja necessário executar algumas etapas pós-migração se tiver personalizado o seguinte em seu ambiente herdado:'
ms.openlocfilehash: 0ef965ef67393604e257049681a64ffb3c5b8fb1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599716"
---
# <a name="migrate-address-book"></a>Migrar o Catálogo de Endereços

Em geral, o Livro de Endereços é migrado juntamente com o restante de sua topologia. No entanto, talvez seja necessário executar algumas etapas pós-migração se tiver personalizado o seguinte em seu ambiente herdado: 

- Personalizou as regras de normalização do Catálogo de Endereços

- Alterou o valor padrão do parâmetro **UseNormalizationRules** para Falso. 


 **Regras de Normalização do Catálogo de Endereços**

Se você personalizava as regras de normalização do Livro de Endereços em seu ambiente herdado, você deve migrar as regras personalizadas para o pool piloto. Se você não personalizou regras de normalização do Catálogo de Endereços, não há nada para migrar para o serviço do Catálogo de Endereços. As regras de normalização padrão para Skype for Business Server 2019 são as mesmas que as regras padrão para a instalação herdda. Siga o procedimento posteriormente nesta seção para migrar regras de normalização personalizadas.

> [!NOTE]
> Se sua organização usa controle de chamadas remotas e você personalizou regras de normalização do Catálogo de Endereços, deve executar o procedimento deste tópico antes de usar o controle de chamadas remotas. O procedimento requer a associação no grupo RTCUniversalServerAdmins ou direitos equivalentes. 

 **UseNormalizationRules definido como Falso**

Se você definir o valor para **UseNormalizationRules** como False para que os usuários possam usar números de telefone como são definidos nos Serviços de Domínio do Active Directory sem que o Skype for Business Server 2019 aplique regras de normalização, você precisará definir os parâmetros **UseNormalizationRules** e **IgnoreGenericRules** como True. Siga o procedimento posteriormente nesta seção para definir esses parâmetros como Verdadeiro. 

## <a name="to-migrate-address-book-customized-normalization-rules"></a>Para migrar regras de normalização personalizadas do Catálogo de Endereços

1. Encontre o arquivo Company_Phone_Number_Normalization_Rules.txt na raiz da pasta compartilhada do Livro de Endereços e copie-o para a raiz da pasta compartilhada do Livro de Endereços no pool piloto Skype for Business Server 2019.

    > [!NOTE]
    > The sample Address Book normalization rules have been installed in your ABS Web component file directory. O caminho é **$installedDriveLetter:\Arquivos de Programas\Microsoft Skype for Business Server 2019\Componentes da Web\Arquivos** do Livro de Endereços\Arquivos\ Sample_Company_Phone_Number_Normalization_Rules.txt. Esse arquivo pode ser copiado e renomeado como **Company_Phone_Number_Normalization_Rules.txt** para o diretório raiz da pasta raiz do livro de endereços compartilhado. Por exemplo, o livro de endereços compartilhado em **$serverX**, o caminho será semelhante **\\ a: $serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**. 

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

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar,** clique em Todos os **Programas,** clique em **Microsoft Skype for Business Server 2019** e clique em Skype for Business Server **Shell de Gerenciamento.**

2. Faça um dos seguintes:

   - Se sua implantação incluir apenas Skype for Business Server 2019, execute o seguinte cmdlet no nível global para alterar os valores de **UseNormalizationRules** e **IgnoreGenericRules** para True: 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - Se sua implantação incluir uma combinação de Skype for Business Server 2019 e uma instalação herdada, execute o seguinte cmdlet e atribua-o a cada pool Skype for Business Server 2019 na topologia:

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. Aguarde a replicação do armazenamento de Gerenciamento Central ocorrer em todos os pools.

4. Modifique o arquivo de regras de normalização de telefone, "Company_Phone_Number_Normalization_Rules.txt", para sua implantação apagar o conteúdo. O arquivo está no compartilhamento de arquivos de cada pool Skype for Business Server 2019. Se o arquivo não estiver presente, crie então um arquivo vazio chamado "Company_Phone_Number_Normalization_Rules.txt".

5. Aguarde vários minutos para que todos os pools de Front-End leiam os novos arquivos.

6. Execute o seguinte cmdlet em cada pool Skype for Business Server 2019 em sua implantação:

   ```PowerShell
   Update-CsAddressBook
   ```


