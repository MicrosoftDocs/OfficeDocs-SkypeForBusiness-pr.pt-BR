---
title: Configurar Skype para Business Server usar o arquivamento do Exchange Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
description: 'Resumo: Configure transcrições de mensagens Instantâneas para o Exchange Server 2016 ou Exchange Server 2013 e Skype para Business Server.'
ms.openlocfilehash: 63d533091426fe609932de18e3d37bd75004ce4c
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23258022"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a>Configurar Skype para Business Server usar o arquivamento do Exchange Server

**Resumo:** Configure o transcrições de mensagens Instantâneas do Exchange Server 2016 ou Exchange Server 2013 e Skype para Business Server.

Skype para Business Server oferece aos administradores a opção de configurar mensagens instantâneas e transcrições de conferência Web arquivadas 2016 do Exchange Server ou o Exchange Server 2013 correio de um usuário ao invés de um banco de dados do SQL Server. Se você habilitar essa opção, as transcrições serão gravadas na Pasta de limpeza do usuário. A Pasta de limpeza é uma pasta oculta encontrada na pasta Itens Recuperáveis. Embora essa pasta não estiver visível aos usuários finais, a pasta é indexada pelo mecanismo de pesquisa do Exchange e pode ser descoberta usando a pesquisa de caixas de correio do Exchange e/ou o Microsoft SharePoint Server 2013. Porque as informações são armazenadas na mesma pasta usada pelo recurso de bloqueio de In-loco do Exchange (responsável para arquivamento de email e outras comunicações do Exchange), os administradores podem usar uma única ferramenta para procurar todas as comunicações eletrônicas arquivados para um usuário.

> [!IMPORTANT]
> Para desabilitar completamente o arquivamento de conversas, você também deverá desabilitar o histórico da conversa. Para obter mais informações, consulte os seguintes tópicos: [Gerenciando o arquivamento de comunicações internas e externas no Skype para Business Server](https://technet.microsoft.com/library/6c2cf941-3204-4f1a-a7e0-416c828056d9.aspx), [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps)e [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).

Para arquivar as transcrições ao Exchange Server, você deve começar por configurar a autenticação servidor-para-servidor entre Skype para Business Server e o Exchange Server. Após a autenticação de servidor-para-servidor no lugar, você pode então realizar as seguintes tarefas no Skype para Business Server (Observe que, dependendo do programa de instalação e configuração, você talvez não precisará concluir todas essas tarefas):

1. Habilite o arquivamento do Exchange, modificando sua Skype para definições de configuração de arquivamento do servidor de negócios. Esta etapa é obrigatória para todas as implantações.

2. Habilitar o arquivamento de comunicações internas e/ou externas dos usuários. Esta etapa é obrigatória para todas as implantações.

3. Configurar a propriedade ExchangeArchivingPolicy para cada usuário. Esta etapa só será necessária se Skype para Business Server e o Exchange Server estão localizados em florestas diferentes.

## <a name="step-1-enabling-exchange-archiving"></a>Etapa 1: Habilitar o arquivamento do Exchange

Arquivamento no Skype para Business Server principalmente é gerenciado usando as definições de configuração de arquivamento. Quando você instala o Skype para Business Server recebem automaticamente uma única coleção global dessas configurações. (Os administradores podem opcionalmente criar novas coleções de definições de arquivamento no escopo do site.) Por padrão, o arquivamento não estiver habilitado nas configurações globais, nem é arquivamento do Exchange habilitado nessas configurações. Para usar o arquivamento do Exchange, administradores devem configurar o EnableArchiving e as propriedades de EnableExchangeArchiving nessas definições de configuração. A propriedade EnableArchiving pode ser definida como um destes três valores:

- **Nenhum**. O Arquivamento está desabilitado. Este é o valor padrão. Se EnableArchiving estiver definido como None, nada serão arquivadas em qualquer um sua Skype para o banco de dados de arquivamento do Business Server ou no Exchange Server.

- **ImOnly**. Apenas transcrições de mensagem instantânea são arquivadas. Se o arquivamento do Exchange estiver habilitado, essas transcrições serão arquivadas no Exchange Server. Se o arquivamento do Exchange estiver desabilitado, em seguida, essas transcrições serão arquivadas no Skype para Business Server.

- **ImAndWebConf**. As transcrições de mensagens instantâneas e Webconferências são arquivadas. Se o arquivamento do Exchange estiver habilitado essas transcrições serão arquivadas no Exchange Server. Se o arquivamento do Exchange estiver desabilitado, em seguida, essas transcrições serão arquivadas no Skype para Business Server.

A propriedade EnableExchangeArchiving é um valor booleano: defina EnableExchangeArchiving como True ($True) para habilitar o arquivamento do Exchange ou definir EnableExchangeArchiving como False ($False) para desabilitar o arquivamento do Exchange. Por exemplo, este comando habilita o arquivamento das transcrições de mensagens instantâneas e também habilita o arquivamento do Exchange:

```
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

Para desabilitar o arquivamento do Exchange, use um comando semelhante ao seguinte, que habilita o arquivamento de mensagens instantâneas, mas desabilita o arquivamento para Exchange (em outras palavras, transcrições serão arquivadas no Skype para Business Server):

```
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> Se a propriedade EnableArchiving estiver definida como nenhuma, então Skype para Business Server não arquivará mensagens instantâneas e transcrições de conferência da Web nisso. Nesse caso, o servidor simplesmente ignorará o valor configurado para EnableExchangeArchiving.

Arquivamento do Exchange pode também ser habilitada (ou desabilitada) usando o Skype para Business Server. Para fazer isso, execute o seguinte procedimento:

1. No Painel de Controle, clique em **Monitoramento e Arquivamento** e, em seguida, clique em **Configuração de Arquivamento**.

2. Na guia **Configuração de Arquivamento**, clique duas vezes no conjunto de configurações de arquivamento a ser modificado (por exemplo, o conjunto **Global**).

3. No painel **Editar Configuração de Arquivamento**, clique na lista suspensa **Configuração de arquivamento** e selecione **Arquivar sessões de IM** (para arquivar apenas sessões de mensagens instantâneas) ou **Arquivar sessões de IM e Webconferência** (para arquivar sessões de mensagens instantâneas e de Webconferência).

4. Depois de escolher os itens a serem arquivados, marque a caixa de seleção **integração do Exchange Server** para habilitar o arquivamento do Exchange. Para desabilitar o arquivamento do Exchange, desmarque esta caixa de seleção.

> [!NOTE]
> A caixa de seleção **Integração com o Exchange Server** não estará disponível se a opção **Configuração de arquivamento** estiver definida como **Desabilitar arquivamento**. Você deve habilitar o arquivamento primeiro e, em seguida, habilitar o arquivamento do Exchange.

Se Skype para Business Server e o Exchange Server está localizado na mesma floresta, em seguida, arquivamento para usuários individuais (ou pelo menos para usuários que possuem o email de contas no Exchange Server) é gerenciada por meio de políticas de retenção de In-loco do Exchange. Se você tiver usuários hospedados em uma versão anterior do Exchange, arquivamento, em seguida, para esses usuários serão gerenciados usando Skype para políticas de arquivamento do servidor de negócios. Observe que apenas os usuários com contas no Exchange Server 2016 ou Exchange Server 2013 podem ter seu Skype para transcrições de negócios arquivadas no Exchange.

Se Skype para Business Server e o Exchange Server estiverem localizado em florestas diferentes, e em seguida, o arquivamento para usuários individuais é gerenciado, definindo a propriedade ExchangeArchivingPolicy para cada conta de usuário individual. Consulte a Etapa 3 para obter mais informações.

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>Etapa 2: Habilitar o arquivamento de comunicações internas e/ou externas

Depois que você tiver habilitado o arquivamento (e arquivamento do Exchange) você deve modificar as políticas de arquivamento apropriadas para garantir que as sessões de usuário, na verdade, serão arquivadas. Observe que simplesmente habilitar o arquivamento (etapa 1) não causa Skype para Business Server para começar o arquivamento de mensagens instantâneas e transcrições de conferência da Web. Em vez disso, você deverá usar políticas de arquivamento para habilitar o arquivamento interno e/ou externo. Quando você instala o Skype para Business Server, você também instalar uma política única e global de arquivamento que contém duas propriedades:

- **ArchiveInternal**. Quando definida como True ($True), indica que as sessões de comunicação interna envolvendo apenas usuários com contas do Active Directory em sua organização serão arquivadas.

- **ArchiveExternal**. Quando definida como True ($True), indica que as sessões de comunicação interna (sessões envolvendo pelo menos um usuário que não possui uma conta do Active Directory em sua organização) serão arquivadas.

Por padrão, os valores de ambas as propriedade são definidos como False, indicando que nem as sessões de comunicação interna nem externa são arquivadas. Para modificar a política global, você pode usar o Skype para Business Server Management Shell e o cmdlet Set-CsArchivingPolicy. Este comando habilita o arquivamento das sessões de comunicação interna e externa:

```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

Como alternativa, é possível usar New-CsArchivingPolicy para criar uma nova política no escopo do site ou no escopo por usuário. Por exemplo, este comando cria uma nova política de arquivamento por usuário chamada RedmondArchivingPolicy:

```
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True
```

Se você criar uma política por usuário, precisará atribuir esta política para os usuários adequados. Por exemplo:

```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"
```

Políticas de arquivamento também podem ser gerenciadas usando o Skype para painel de controle do servidor de negócios. No Painel de Controle, clique em **Monitoramento e Arquivamento** e em **Política de Arquivamento**. Para modificar uma política existente, clique duas vezes na política (por exemplo, Global) e, no painel **Editar Política de Arquivamento**, marque ou desmarque as caixas de seleção **Arquivar comunicações internas** e **Arquivar comunicações externas**, conforme necessário. Para criar uma nova política de arquivamento, clique em **novo** e, em seguida, selecione a **política de Site** ou **política de usuário**. Se você criar uma nova política de usuário, deverá acessar as contas de usuário adequadas (na guia **Usuários**) e atribuir a nova política a esses usuários.

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>Etapa 3: Configurar a propriedade ExchangeArchivingPolicy

Se Skype para Business Server e o Exchange Server estiverem localizado em florestas diferentes, em seguida, não é suficiente permitir que apenas as definições de configuração de arquivamento; de arquivamento do Exchange que não resultará em mensagens instantâneas e transcrições de conferência Web sendo arquivadas no Exchange. Em vez disso, você também deve configurar a propriedade ExchangeArchivingPolicy em cada um do Skype relevante para contas de usuário do servidor de negócios. Essa propriedade pode ser definida como um destes quatro valores:

1. **Não inicializado**. Indica que arquivamento será baseado nas configurações de bloqueio In-loco configuradas para a caixa de correio do Exchange do usuário; Se o bloqueio In-loco não foi habilitado na caixa de correio do usuário e em seguida, o usuário terá sua mensagem e Web transcrições de conferência arquivadas no Skype para Business Server.

2. **UseLyncArchivingPolicy**. Indica que o usuário de mensagens instantâneas e transcrições de conferência Web devam ser arquivadas no Skype para Business Server e não em Exchange.

3. **NoArchiving**. Indica que as transcrições de mensagens instantâneas e Webconferências do usuário não devem ser arquivadas. Observe que essa configuração substitui qualquer Skype para Business Server atribuídas ao usuário de políticas de arquivamento.

4. **ArchivingToExchange**. Indica que o usuário de mensagens instantâneas e webconferência transcrições devam ser arquivadas para o Exchange, independentemente das configurações de bloqueio In-loco que têm (ou não) foi atribuído à caixa de correio do usuário.

Por exemplo, para configurar uma conta de usuário para que as mensagens instantâneas e transcrições de conferência da Web sejam sempre arquivadas no Exchange, você pode usar um comando semelhante a este no Skype do Shell de gerenciamento do servidor de negócios:

```
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

Se desejar definir a mesma política de arquivamento para um grupo de usuários (por exemplo, todos os usuários hospedados em um pool de Registradores Avançados especificado), você poderá usar um comando semelhante ao seguinte:

```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

Observe que você deve usar o Skype para Business Server Management Shell (e o Windows PowerShell) para configurar o valor da propriedade ExchangeArchivingPolicy. Essa propriedade não é exposta aos administradores no Skype para Business Server.

Se desejar exibir uma lista de todos os usuários aos quais foi atribuída uma política de arquivamento específica, você poderá usar um comando semelhante ao apresentando a seguir, que retorna o nome para exibição do Active Directory de todos os usuários que tiveram a propriedade ExchangeArchivingPolicy definida como Não inicializado:

```
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

Da mesma forma, este comando retorna o nome para exibição dos usuários que não têm a propriedade ExchangeArchivingPolicy definida como UseLyncArchivingPolicy:

```
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```


