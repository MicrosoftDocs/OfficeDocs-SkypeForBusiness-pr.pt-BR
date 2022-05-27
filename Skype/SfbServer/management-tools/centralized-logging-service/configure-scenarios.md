---
title: Configurar cenários para o Serviço de Log Centralizado no Skype for Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: 'Resumo: saiba como criar, modificar e remover cenários para o Serviço de Log Centralizado no Skype for Business Server 2015.'
ms.openlocfilehash: ecd96dc849030cb035f965c8cb52eb7607bd9667
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676353"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Configurar cenários para o Serviço de Log Centralizado no Skype for Business Server 2015

**Resumo:** Saiba como criar, modificar e remover cenários para o Serviço de Log Centralizado no Skype for Business Server 2015.

Os cenários definem o escopo (ou seja, global, site, pool ou computador) e quais provedores usar no Serviço de Log Centralizado. Usando cenários, você habilita e desabilita o rastreamento nos provedores (por exemplo, S4, SIPStack, mensagens instantâneas e presença). Ao configurar um cenário, você pode agrupar todos os provedores de determinado conjunto lógico que tratam um problema específico. Se você achar que um cenário precisa ser modificado para atender às suas necessidades de solução de problemas e registro em log, as Ferramentas de Depuração do Skype for Business Server 2015 fornecerão um módulo de Windows PowerShell chamado ClsScenarioEdit.psm1 que contém uma função chamadaEdit-CsClsScenario. A finalidade desse módulo é editar as propriedades do cenário nomeado. Neste tópico, serão fornecidos exemplos de como esse módulo funciona. Baixe as Skype for Business Server ferramentas de [depuração](https://go.microsoft.com/fwlink/p/?LinkId=285257) do Skype for Business Server 2015 antes de continuar.

> [!IMPORTANT]
> Para qualquer dado escopo (global, site, pool ou computador), é possível executar no máximo dois cenários por vez. Para determinar quais cenários estão em execução no momento, use Windows PowerShell [Get-CsClsScenario](/powershell/module/skype/get-csclsscenario). Usando Windows PowerShell [e Set-CsClsScenario](/powershell/module/skype/set-csclsscenario), você pode alterar dinamicamente quais cenários estão em execução. Você pode modificar quais cenários estão em execução durante uma sessão de registro em log para ajustar ou refinar os dados coletados e de quais provedores.

Para executar as funções do Serviço de Log Centralizado usando o Shell de Gerenciamento do Skype for Business Server, você deve ser membro dos grupos de segurança CsAdministrator ou RBAC (controle de acesso baseado em função) CsServerAdministrator ou uma função RBAC personalizada que contenha qualquer um desses dois grupos. Para retornar uma lista de todas as funções RBAC às qual esse cmdlet foi atribuído, incluindo quaisquer funções RBAC personalizadas que você mesmo criou, execute o seguinte comando no Shell de Gerenciamento do Skype for Business Server ou no prompt Windows PowerShell:

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Por exemplo:

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

O restante deste tópico se concentra em como definir um cenário, modificar um cenário, recuperar quais cenários estão em execução, remover um cenário e especificar o que um cenário contém para otimizar a solução de problemas. Você pode usar o shell Skype for Business Server gerenciamento para emitir Windows PowerShell comandos. Ao usar Windows PowerShell, você pode definir novos cenários para uso em suas sessões de log.

Conforme introduzido no [Serviço de Log Centralizado Skype for Business 2015](centralized-logging-service.md), os elementos de um cenário são:

- **Provedores** Se você estiver familiarizado com o OCSLogger, os provedores são os componentes que você opta por informar ao OCSLogger do que o mecanismo de rastreamento deve coletar logs. Os provedores são os mesmos componentes e, em muitos casos, têm o mesmo nome que os componentes do OCSLogger. Se você não estiver familiarizado com o OCSLogger, os provedores serão componentes específicos da função de servidor dos qual o Serviço de Log Centralizado pode coletar logs. Para obter detalhes sobre a configuração de provedores, consulte [Configurar provedores para o Serviço de Log Centralizado no Skype for Business Server 2015](configure-providers.md).

- **Identidade** O parâmetro -Identity define o escopo e o nome do cenário. Por exemplo, você pode definir um escopo "global" e identificar o cenário com "LyssServiceScenario". Ao combinar os dois, você define a Identidade (por exemplo, "global/LyssServiceScenario").

    Opcionalmente, você pode usar os parâmetros -Name e -Parent. Você define o parâmetro Name para identificar exclusivamente o cenário. Se usá-lo, também deverá usar Parent para adicionar o cenário ao escopo global ou site.

    > [!IMPORTANT]
    > Se você usar os parâmetros Nome e Pai, não poderá usar **o parâmetro -** Identity.

## <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>Para criar um novo cenário com o cmdlet New-CsClsScenario

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, clique** em Todos os **Programas, clique** em **Skype for Business 2015** e, em seguida, clique **Skype for Business Server Shell de Gerenciamento**.

2. Para criar um novo cenário para uma sessão de registro em log, use [New-CsClsProvider](/powershell/module/skype/new-csclsprovider) e defina o nome do cenário (ou seja, como ele será identificado exclusivamente). Escolha um tipo de formato de registro em log entre WPP (ou seja, o pré-processador de rastreamento de software do Windows, que é o padrão), EventLog (ou seja, o formato de log de eventos do Windows) ou IISLog (ou seja, o arquivo de formato ASCII baseado no formato de arquivo de log do IIS). Em seguida, defina o nível (conforme definido em Níveis de registro em log neste tópico) e os sinalizadores (conforme definido em Sinalizadores neste tópico).

    Para este cenário de exemplo, usaremos LyssProvider como a variável de provedor de exemplo.

    Para criar um cenário usando as opções definidas, digite:

   ```PowerShell
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    Por exemplo:

   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    O formato alternativo usando -Name e -Parent:

   ```PowerShell
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

## <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>Para criar um novo cenário com vários provedores usando o cmdlet New-CsClsScenario

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, clique** em Todos os **Programas, clique** em **Skype for Business 2015** e, em seguida, clique **Skype for Business Server Shell de Gerenciamento**.

2. Há um limite de dois cenários por escopo. No entanto, não há um limite quanto ao número de provedores. Neste exemplo, suponha que criamos três provedores e você deseja atribuir todos eles ao cenário que está definindo. Os nomes das variáveis dos provedores são LyssProvider, ABServerProvider e SIPStackProvider. Para definir e atribuir vários provedores a um cenário, digite o seguinte em um shell de gerenciamento Skype for Business Server ou Windows PowerShell prompt de comando:

   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > Como é conhecido no Windows PowerShell, a convenção para criar uma tabela de hash `@{<variable>=<value1>, <value2>, <value>...}` de valores usando é conhecida como nivelamento. Para obter detalhes sobre o nivelamento Windows PowerShell, consulte [https://go.microsoft.com/fwlink/p/?LinkId=267760](/previous-versions/technet-magazine/gg675931(v=msdn.10)).

## <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>Para modificar um cenário existente com o cmdlet Set-CsClsScenario

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, clique** em Todos os **Programas, clique** em **Skype for Business 2015** e, em seguida, clique **Skype for Business Server Shell de Gerenciamento**.

2. Há um limite de dois cenários por escopo. Você pode alterar quais cenários estão em execução a qualquer momento, mesmo quando uma sessão de coleta de log está em andamento. Se você redefinir os cenários em execução, a sessão de registro em log atual parará de usar o cenário que foi removido e começará a usar o novo cenário. No entanto, as informações de log que já foram coletadas com o cenário removido permanecerão nos logs coletados. Para definir um novo cenário, faça o seguinte (ou seja, supondo a adição de um provedor já definido chamado "S4Provider"):

   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    Por exemplo:

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    Se você desejar substituir provedores, defina um único provedor ou uma lista separada por vírgulas de provedores para substituir o conjunto atual. Se você desejar substituir apenas um de vários provedores, adicione os provedores atuais junto com os novos provedores para criar um novo conjunto de provedores que contenha os provedores novos e existentes. Para substituir todos os provedores por um novo conjunto, digite o seguinte:

   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    Por exemplo, para substituir o conjunto atual de $LyssProvider, $ABServerProvider e $SIPStackProvider por $LyssServiceProvider:

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    Para substituir apenas o provedor $LyssProvider do conjunto atual de $LyssProvider, $ABServerProvider e $SIPStackProvider por $LyssServiceProvider, digite o seguinte:

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

## <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>Para remover um cenário existente com o cmdlet Remove-CsClsScenario

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, clique** em Todos os **Programas, clique** em **Skype for Business 2015** e, em seguida, clique **Skype for Business Server Shell de Gerenciamento**.

2. Se você desejar remover um cenário que foi definido anteriormente, digite o seguinte:

   ```PowerShell
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    Por exemplo, para remover o cenário definido site:Redmond/LyssServiceScenario:

   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

O cmdlet **Remove-CsClsScenario** remove o cenário especificado, mas os rastreamentos que foram coletados ainda estarão disponíveis nos logs para pesquisa.

## <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a>Para carregar e descarregar o cmdlet Edit-CsClsScenario usando o módulo ClsScenarioEdit.psm1

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, clique** em Todos os **Programas, clique** em **Skype for Business 2015** e, em seguida, clique **Skype for Business Server Shell de Gerenciamento**.

    > [!IMPORTANT]
    > O módulo ClsScenarioEdit.psm1 é fornecido como um download da Web separado. O módulo faz parte das ferramentas de depuração Skype for Business Server 2015. Por padrão, as ferramentas de depuração são instaladas no diretório C:\Arquivos de Programas\Skype for Business Server 2015\Ferramentas de Depuração.

2. No Windows PowerShell, digite:

   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > O carregamento bem-sucedido do módulo retorna você para o prompt Windows PowerShell comando. Para confirmar se o módulo foi carregado e se Edit-CsClsScenario está disponível, digite  `Get-Help Edit-CsClsScenario`. Você deverá ver a sinopse básica da sintaxe de EditCsClsScenario.

3. Para descarregar os módulos, digite:

   ```PowerShell
   Remove-Module ClsController
   ```

    > [!TIP]
    > O descarregamento bem-sucedido do módulo retorna você para o prompt Windows PowerShell comando. Para confirmar se o módulo foi descarregado, digite  `Get-Help Edit-CsClsScenario`. Windows PowerShell tentar localizar a ajuda para o cmdlet e falhar.

## <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>Para remover um provedor existente de um cenário com o módulo Edit-ClsController

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, clique** em Todos os **Programas, clique** em **Skype for Business 2015** e, em seguida, clique **Skype for Business Server Shell de Gerenciamento**.

2. No Windows PowerShell, digite:

   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > O carregamento bem-sucedido do módulo retorna você para o prompt Windows PowerShell comando. Para confirmar se o módulo foi carregado e se Edit-CsClsScenario está disponível, digite  `Get-Help Edit-CsClsScenario`. Você deverá ver a sinopse básica da sintaxe de EditCsClsScenario.

3. Para remover um provedor do cenário AlwaysOn, digite:

   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   Por exemplo:

   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   Os parâmetros ScenarioName e ProviderName são posicionais (ou seja, devem ser definidos na posição esperada na linha de comando). O nome do parâmetro não precisa ser explicitamente definido se o nome do cenário estiver na segunda ou na terceira posição em relação ao nome do cmdlet na primeira posição. Usando essas informações, o comando anterior seria digitado como:

   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   A colocação posicional dos valores de parâmetro se aplica somente a -Scenario e -Provider. Todos os outros parâmetros devem ser definidos explicitamente.

## <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>Para adicionar um provedor a um cenário com o cmdlet Edit-ClsController

1. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, clique** em Todos os **Programas, clique** em **Skype for Business 2015** e, em seguida, clique **Skype for Business Server Shell de Gerenciamento**.

2. Para adicionar um provedor ao cenário AlwaysOn, digite:

   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    Por exemplo:

   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    -Loglevel pode ser do tipo Fatal, Error, Warning, Info, Verbose, Debug ou All. -Sinalizadores podem ser qualquer um dos sinalizadores que o provedor dá suporte, como TF_COMPONENT, TF_DIAG. -Sinalizadores também podem ser de valor ALL

   O exemplo anterior também pode ser digitado com o uso do recurso posicional do cmdlet. Por exemplo, para adicionar o provedor ChatServer ao cenário AlwaysOn, digite:

   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```
