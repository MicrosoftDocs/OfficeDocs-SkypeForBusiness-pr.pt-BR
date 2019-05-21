---
title: Configurar o Skype for Business Server para usar o arquivamento do Exchange Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
description: 'Resumo: configurar transcrições de mensagens instantâneas do Exchange Server 2016 ou do Exchange Server 2013 e do Skype for Business Server.'
ms.openlocfilehash: b24353a9742a48b35e21ac00df40a04fa60e444b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278067"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a>Configurar o Skype for Business Server para usar o arquivamento do Exchange Server

**Resumo:** Configurar transcrições de mensagens instantâneas para o Exchange Server 2016 ou o Exchange Server 2013 e o Skype for Business Server.

O Skype for Business Server oferece aos administradores a opção de ter mensagens instantâneas e transcrições de webconferências arquivadas em uma caixa de correio do Exchange Server 2016 ou do Exchange Server 2013 do usuário, em vez de um banco de dados do SQL Server. Se você habilitar essa opção, as transcrições serão gravadas na Pasta de limpeza do usuário. A Pasta de limpeza é uma pasta oculta encontrada na pasta Itens Recuperáveis. Embora essa pasta não seja visível para os usuários finais, a pasta é indexada pelo mecanismo de pesquisa do Exchange e pode ser descoberta usando a pesquisa da caixa de correio do Exchange e/ou o Microsoft SharePoint Server 2013. Como as informações são armazenadas na mesma pasta usada pelo recurso bloqueio in-loco do Exchange (responsável pelo arquivamento de email e outras comunicações do Exchange), os administradores podem usar uma única ferramenta para pesquisar todas as comunicações eletrônicas arquivadas para um utilizador.

> [!IMPORTANT]
> Para desabilitar completamente o arquivamento de conversas, você também deverá desabilitar o histórico da conversa. Para obter mais informações, consulte os tópicos a seguir: [gerenciar o arquivamento de comunicações internas e externas no Skype for Business Server](https://technet.microsoft.com/library/6c2cf941-3204-4f1a-a7e0-416c828056d9.aspx), [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps)e [set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).

Para arquivar transcrições no Exchange Server, você deve começar Configurando a autenticação de servidor para servidor entre o Skype for Business Server e o Exchange Server. Após a autenticação do servidor para o servidor estar em vigor, você pode executar as seguintes tarefas no Skype for Business Server (Observe que, dependendo da configuração e da configuração, talvez você não precise completar todas essas tarefas):

1. Habilite o arquivamento do Exchange modificando as configurações de arquivamento do Skype for Business Server. Esta etapa é obrigatória para todas as implantações.

2. Habilitar o arquivamento de comunicações internas e/ou externas dos usuários. Esta etapa é obrigatória para todas as implantações.

3. Configurar a propriedade ExchangeArchivingPolicy para cada usuário. Esta etapa só será necessária se o Skype for Business Server e o Exchange Server estiverem localizados em florestas diferentes.

## <a name="step-1-enabling-exchange-archiving"></a>Etapa 1: habilitar o arquivamento do Exchange

O arquivamento no Skype for Business Server é essencialmente gerenciado usando-se as configurações de arquivamento de configuração. Ao instalar o Skype for Business Server, você recebe automaticamente uma única coleção global dessas configurações. (Os administradores podem, opcionalmente, criar novas coleções de configurações de arquivamento no escopo do site.) Por padrão, o arquivamento não está habilitado nas configurações globais, nem o arquivamento do Exchange está habilitado nessas configurações. Para usar o arquivamento do Exchange, os administradores devem configurar as propriedades EnableArchiving e EnableExchangeArchiving nesses parâmetros de configuração. A propriedade EnableArchiving pode ser definida como um destes três valores:

- **Nenhum**. O Arquivamento está desabilitado. Este é o valor padrão. Se EnableArchiving estiver definido como None, nada será arquivado no banco de dados de arquivamento do Skype for Business Server ou no Exchange Server.

- **ImOnly**. Apenas transcrições de mensagem instantânea são arquivadas. Se o arquivamento do Exchange estiver habilitado, essas transcrições serão arquivadas no Exchange Server. Se o arquivamento do Exchange estiver desabilitado, essas transcrições serão arquivadas no Skype for Business Server.

- **ImAndWebConf**. As transcrições de mensagens instantâneas e Webconferências são arquivadas. Se o arquivamento do Exchange estiver habilitado, essas transcrições serão arquivadas no Exchange Server. Se o arquivamento do Exchange estiver desabilitado, essas transcrições serão arquivadas no Skype for Business Server.

A propriedade EnableExchangeArchiving é um valor booliano: defina EnableExchangeArchiving como true ($True) para habilitar o arquivamento do Exchange ou defina EnableExchangeArchiving como false ($False) para desabilitar o arquivamento do Exchange. Por exemplo, esse comando permite o arquivamento de transcrições de mensagens instantâneas e também permite o arquivamento do Exchange:

```
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

Para desabilitar o arquivamento do Exchange, use um comando semelhante ao seguinte, que permite o arquivamento de mensagens instantâneas, mas que desabilite o arquivamento no Exchange (em outras palavras, as transcrições serão arquivadas no Skype for Business Server):

```
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> Se a propriedade EnableArchiving estiver definida como None, o Skype for Business Server não arquivará mensagens instantâneas e transcrições da Webconferência. Nesse caso, o servidor simplesmente ignorará o valor configurado para EnableExchangeArchiving.

O arquivamento do Exchange também pode ser habilitado (ou desabilitado) usando o Skype for Business Server. Para fazer isso, execute o seguinte procedimento:

1. No Painel de Controle, clique em **Monitoramento e Arquivamento** e, em seguida, clique em **Configuração de Arquivamento**.

2. Na guia **Configuração de Arquivamento**, clique duas vezes no conjunto de configurações de arquivamento a ser modificado (por exemplo, o conjunto **Global**).

3. No painel **Editar Configuração de Arquivamento**, clique na lista suspensa **Configuração de arquivamento** e selecione **Arquivar sessões de IM** (para arquivar apenas sessões de mensagens instantâneas) ou **Arquivar sessões de IM e Webconferência** (para arquivar sessões de mensagens instantâneas e de Webconferência).

4. Depois de escolher os itens a serem arquivados, selecione a caixa de seleção **integração do Exchange Server** para habilitar o arquivamento do Exchange. Para desabilitar o arquivamento do Exchange, desmarque esta caixa de seleção.

> [!NOTE]
> A caixa de seleção **Integração com o Exchange Server** não estará disponível se a opção **Configuração de arquivamento** estiver definida como **Desabilitar arquivamento**. Você deve habilitar o arquivamento primeiro e, em seguida, habilitar o arquivamento do Exchange.

Se o Skype for Business Server e o Exchange Server estiverem localizados na mesma floresta, o arquivamento para usuários individuais (ou pelo menos para usuários que tenham contas de email no Exchange Server) será gerenciado com o uso de políticas de bloqueio in-loco do Exchange. Se você tiver usuários que são hospedados em uma versão anterior do Exchange, o arquivamento para esses usuários serão gerenciados usando as políticas de arquivamento do Skype for Business Server. Observe que somente os usuários com contas no Exchange Server 2016 ou Exchange Server 2013 podem ter suas transcrições do Skype for Business arquivadas no Exchange.

Se o Skype for Business Server e o Exchange Server estiverem localizados em florestas diferentes, o arquivamento para usuários individuais será gerenciado com a configuração da propriedade ExchangeArchivingPolicy para cada conta de usuário individual. Consulte a Etapa 3 para obter mais informações.

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>Etapa 2: Habilitar o arquivamento de comunicações internas e/ou externas

Depois de habilitar o arquivamento (e o arquivamento do Exchange), você deve modificar as políticas de arquivamento adequadas para garantir que as sessões do usuário sejam realmente arquivadas. Observe que a simples habilitação do arquivamento (etapa 1) não faz com que o Skype for Business Server comece a arquivar mensagens instantâneas e transcrições da Webconferência. Em vez disso, você deverá usar políticas de arquivamento para habilitar o arquivamento interno e/ou externo. Ao instalar o Skype for Business Server, você também pode instalar uma única política de arquivamento global contendo duas propriedades:

- **ArchiveInternal**. Quando definida como True ($True), indica que as sessões de comunicação interna envolvendo apenas usuários com contas do Active Directory em sua organização serão arquivadas.

- **ArchiveExternal**. Quando definida como True ($True), indica que as sessões de comunicação interna (sessões envolvendo pelo menos um usuário que não possui uma conta do Active Directory em sua organização) serão arquivadas.

Por padrão, os valores de ambas as propriedade são definidos como False, indicando que nem as sessões de comunicação interna nem externa são arquivadas. Para modificar a política global, você pode usar o Shell de gerenciamento do Skype for Business Server e o cmdlet Set-CsArchivingPolicy. Este comando habilita o arquivamento das sessões de comunicação interna e externa:

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

As políticas de arquivamento também podem ser gerenciadas usando o painel de controle do Skype for Business Server. No Painel de Controle, clique em **Monitoramento e Arquivamento** e em **Política de Arquivamento**. Para modificar uma política existente, clique duas vezes na política (por exemplo, Global) e, no painel **Editar Política de Arquivamento**, marque ou desmarque as caixas de seleção **Arquivar comunicações internas** e **Arquivar comunicações externas**, conforme necessário. Para criar uma nova política de arquivamento, clique em **novo** e, em seguida, selecione política de **site** ou **política de usuário**. Se você criar uma nova política de usuário, deverá acessar as contas de usuário adequadas (na guia **Usuários**) e atribuir a nova política a esses usuários.

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>Etapa 3: Configurar a propriedade ExchangeArchivingPolicy

Se o Skype for Business Server e o Exchange Server estiverem localizados em florestas diferentes, não será suficiente simplesmente habilitar o arquivamento do Exchange nas configurações de arquivamento de configuração. Isso não resultará em mensagens instantâneas e transcrições de conferência na Web sendo arquivadas no Exchange. Em vez disso, você também deve configurar a propriedade ExchangeArchivingPolicy em cada uma das contas de usuário relevantes do Skype for Business Server. Essa propriedade pode ser definida como um destes quatro valores:

1. **** Não inicializado. Indica que o arquivamento será baseado nas configurações de bloqueio in-loco definidas para a caixa de correio do Exchange do usuário; Se o bloqueio in-loco não tiver sido habilitado na caixa de correio do usuário, o usuário terá suas transcrições de mensagens e de Webconferência arquivadas no Skype for Business Server.

2. **UseLyncArchivingPolicy**. Indica que as transcrições de mensagens instantâneas e conferência na Web do usuário devem ser arquivadas no Skype for Business Server, em vez de no Exchange.

3. **NoArchiving**. Indica que as transcrições de mensagens instantâneas e Webconferências do usuário não devem ser arquivadas. Observe que essa configuração substitui todas as políticas de arquivamento do Skype for Business Server atribuídas ao usuário.

4. **ArchivingToExchange**. Indica que as transcrições de mensagens instantâneas e webconferências do usuário devem ser arquivadas no Exchange independentemente das configurações de bloqueio in-loco que tiverem (ou não) sido atribuídas à caixa de correio do usuário.

Por exemplo, para configurar uma conta de usuário para que as transcrições de mensagens instantâneas e webconferências sejam sempre arquivadas no Exchange, você pode usar um comando semelhante a este do Shell de gerenciamento do Skype for Business Server:

```
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

Se desejar definir a mesma política de arquivamento para um grupo de usuários (por exemplo, todos os usuários hospedados em um pool de Registradores Avançados especificado), você poderá usar um comando semelhante ao seguinte:

```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

Observe que você deve usar o Shell de gerenciamento do Skype for Business Server (e o Windows PowerShell) para configurar o valor da propriedade ExchangeArchivingPolicy. Essa propriedade não é exposta a administradores no Skype for Business Server.

Se desejar exibir uma lista de todos os usuários aos quais foi atribuída uma política de arquivamento específica, você poderá usar um comando semelhante ao apresentando a seguir, que retorna o nome para exibição do Active Directory de todos os usuários que tiveram a propriedade ExchangeArchivingPolicy definida como Não inicializado:

```
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

Da mesma forma, este comando retorna o nome para exibição dos usuários que não têm a propriedade ExchangeArchivingPolicy definida como UseLyncArchivingPolicy:

```
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```


