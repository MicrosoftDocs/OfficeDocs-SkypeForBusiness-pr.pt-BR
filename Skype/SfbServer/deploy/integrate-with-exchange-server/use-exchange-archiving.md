---
title: Configurar Skype for Business Server para usar Exchange Server arquivamento
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
description: 'Resumo: Configure transcrições de IM para Exchange Server 2016 ou Exchange Server 2013 e Skype for Business Server.'
ms.openlocfilehash: 0b154c9184002cf663d61395277471f8a927c556
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60840583"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a>Configurar Skype for Business Server para usar Exchange Server arquivamento

**Resumo:** Configure transcrições de IM para Exchange Server 2016 ou Exchange Server 2013 e Skype for Business Server.

Skype for Business Server oferece aos administradores a opção de ter transcrições de mensagens instantâneas e webconferências arquivadas na caixa de correio do Exchange Server 2016 ou Exchange Server 2013 de um usuário em vez de um banco de dados SQL Server. Se você habilitar esta opção, as transcrições são gravadas na pasta Lixeira da caixa de correio do usuário. A pasta Lixeira é uma pasta oculta encontrada na pasta Itens Recuperáveis. Embora essa pasta não seja visível para usuários finais, a pasta é indexada pelo mecanismo de pesquisa Exchange e pode ser descoberta usando Exchange pesquisa de caixa de correio e/ou Microsoft SharePoint Server 2013. Como as informações são armazenadas na mesma pasta usada pelo recurso Exchange In-Place Hold (responsável pelo arquivamento de emails e outras comunicações Exchange), os administradores podem usar uma única ferramenta para pesquisar todas as comunicações eletrônicas arquivadas para um usuário.

> [!IMPORTANT]
> Para desabilitar completamente o arquivamento de conversas, você também deve desabilitar o histórico da conversa. Para obter mais informações, consulte os seguintes tópicos: [Managing the Archiving of internal](/previous-versions/office/lync-server-2013/lync-server-2013-managing-the-archiving-of-internal-and-external-communications)and external communications in Skype for Business Server , [New-CsClientPolicy](/powershell/module/skype/new-csclientpolicy?view=skype-ps)e [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps).

Para arquivar transcrições para Exchange Server você deve começar configurando a autenticação de servidor para servidor entre Skype for Business Server e Exchange Server. Depois que a autenticação de servidor para servidor for realizada, você poderá executar as seguintes tarefas no Skype for Business Server (observe que, dependendo da configuração e da configuração, talvez não seja necessário concluir todas essas tarefas):

1. Habilita Exchange arquivamento modificando suas configurações Skype for Business Server de arquivamento. Esta etapa é obrigatória para todas as implantações.

2. Habilitar o arquivamento para comunicações internas e/ou externas dos usuários. Esta etapa é obrigatória para todas as implantações.

3. Configurar a propriedade ExchangeArchivingPolicy para cada usuário. Esta etapa só será necessária se Skype for Business Server e Exchange Server estão localizados em florestas diferentes.

## <a name="step-1-enabling-exchange-archiving"></a>Etapa 1: Habil Exchange arquivamento

O arquivamento no Skype for Business Server é gerenciado principalmente usando as configurações de arquivamento. Quando você instala Skype for Business Server você recebe automaticamente uma única coleção global dessas configurações. (Os administradores podem, opcionalmente, criar novas coleções de configurações de arquivamento no escopo do site.) Por padrão, o arquivamento não está habilitado nas configurações globais, nem Exchange arquivamento habilitado nessas configurações. Para usar Exchange arquivamento, os administradores devem configurar as propriedades EnableArchiving e EnableExchangeArchiving nessas configurações. A propriedade EnableArchiving pode ser definida para um dos seguintes três valores:

- **Nenhum**. o Arquivamento é desabilitado. Este é o valor padrão. Se EnableArchiving estiver definido como Nenhum, nada será arquivado no banco de dados Skype for Business Server de arquivamento ou no Exchange Server.

- **ImOnly**. Apenas transcrições de mensagem instantânea são arquivadas. Se Exchange arquivamento estiver habilitado, essas transcrições serão arquivadas Exchange Server. Se Exchange arquivamento estiver desabilitado, essas transcrições serão arquivadas para Skype for Business Server.

- **ImAndWebConf**. As transcrições de mensagem instantânea e de conferência da Web são arquivadas. Se Exchange arquivamento estiver habilitado, essas transcrições serão arquivadas em Exchange Server. Se Exchange arquivamento estiver desabilitado, essas transcrições serão arquivadas para Skype for Business Server.

A propriedade EnableExchangeArchiving é um valor Boolean: de definir EnableExchangeArchiving como True ($True) para habilitar o arquivamento Exchange ou definir EnableExchangeArchiving como False ($False) para desabilitar Exchange arquivamento. Por exemplo, esse comando habilita o arquivamento de transcrições de mensagens instantâneas e também permite Exchange arquivamento:

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

Para desabilitar Exchange arquivamento, use um comando semelhante ao seguinte, que habilita o arquivamento de mensagens instantâneas, mas desabilita o arquivamento para Exchange (em outras palavras, transcrições serão arquivadas em Skype for Business Server):

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> Se a propriedade EnableArchiving estiver definida como Nenhuma, Skype for Business Server não arquivará as transcrições de mensagens instantâneas e webconferências. Neste caso, o servidor simplesmente ignora o valor configurado para EnableExchangeArchiving.

Exchange arquivamento também pode ser habilitado (ou desabilitado) usando a Skype for Business Server. Para fazer isso, conclua o seguinte procedimento:

1. No Painel de Controle, clique em **Monitoramento e Arquivamento** e clique em **Configuração de Arquivamento**.

2. Na guia **Configuração de Arquivamento**, clique duas vezes no conjunto de configurações de arquivamento a ser modificado (por exemplo, o conjunto **Global**).

3. No painel **Editar configuração de arquivamento**, clique na lista suspensa **Configuração de arquivamento** e selecione **Arquivar sessões de IM** (para arquivar apenas sessões de mensagem instantânea) ou **Arquivar sessões de IM e conferência da Web** (para arquivar sessões de mensagem instantânea e conferência da Web).

4. Depois de escolher os itens a serem arquivados, selecione a caixa de seleção de Exchange Server **de** integração para habilitar Exchange arquivamento. Para desabilitar Exchange arquivamento, desempure essa caixa de seleção.

> [!NOTE]
> A caixa de seleção **Integração do Exchange Server** não estará disponível se a **Configuração de arquivamento** está definido para **Desabilitar arquivamento**. Você deve habilitar o arquivamento primeiro e, em seguida, habilitar Exchange arquivamento.

Se Skype for Business Server e Exchange Server estão localizados na mesma floresta, o arquivamento para usuários individuais (ou pelo menos para usuários que possuem contas de email no Exchange Server) é gerenciado usando as políticas de Exchange In-Place Hold. Se você tiver usuários que estão em uma versão anterior do Exchange, o arquivamento desses usuários será gerenciado usando Skype for Business Server de arquivamento. Observe que apenas usuários com contas no Exchange Server 2016 ou Exchange Server 2013 podem ter suas transcrições Skype for Business arquivadas em Exchange.

Se Skype for Business Server e Exchange Server estão localizados em florestas diferentes, o arquivamento para usuários individuais é gerenciado configurando a propriedade ExchangeArchivingPolicy para cada conta de usuário individual. Consulte a Etapa 3 para obter mais informações.

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>Etapa 2: Habilitar o arquivamento de comunicações internas e/ou externas

Depois de habilitar o arquivamento (e Exchange arquivamento) você deve modificar as políticas de arquivamento apropriadas para garantir que as sessões do usuário sejam realmente arquivadas. Observe que a simples habilitação do arquivamento (Etapa 1) não faz com que Skype for Business Server inicie o arquivamento de mensagens instantâneas e transcrições de webconferência. Ao invés disso, você deve usar políticas de arquivamento para habilitar o arquivamento interno e/ou externo. Quando você instala Skype for Business Server também instala uma única política de arquivamento global que contém duas propriedades:

- **ArchiveInternal**. Quando definido para True ($True) indica que as sessões de comunicação interna envolvendo apenas usuários com contas do Active Directory em sua organização serão arquivadas.

- **ArchiveExternal**. Quando definido para True ($True) indica que as sessões de comunicação interna (sessões envolvendo pelo menos um usuário que não possui uma conta do Active Directory em sua organização) serão arquivadas.

Por padrão, ambos os valores de propriedade são definidos para False, significando que as sessões de comunicação interna e externa não são arquivadas. Para modificar a política global, você pode usar o Shell de Gerenciamento Skype for Business Server e o cmdlet Set-CsArchivingPolicy usuário. Este comando habilita o arquivamento de sessões de comunicação interna e externa:

```powershell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

Em alternativa, é possível usar New-CsArchivingPolicy para criar uma nova política no escopo local ou no escopo por usuário. Por exemplo, este comando cria uma nova política de arquivamento por usuário chamada RedmondArchivingPolicy:

```powershell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True
```

Se você criar uma política por usuário, precisará atribuir esta política para os usuários adequados. Por exemplo:

```powershell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"
```

As políticas de arquivamento também podem ser gerenciadas usando o Painel Skype for Business Server Controle. Dentro do Painel de Controle, clique em **Monitoramento e Arquivamento** e em **Política de Arquivamento**. Para modificar uma política existente, clique duas vezes na política (por exemplo, Global) e, no painel **Editar política de arquivamento**, marque ou desmarque as caixas de seleção **Arquivar comunicações internas** e **Arquivar comunicações externas** conforme necessário. Para criar uma nova política de arquivamento, clique em **Novo** e selecione Política **de site** ou Política **de usuário.** Se você criar uma nova política de usuário, deve acessar as contas de usuário adequadas (na guia **Usuários**) e atribuir estes usuários com a nova política.

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>Etapa 3: Configurar a propriedade ExchangeArchivingPolicy

Se Skype for Business Server e Exchange Server estão localizados em florestas diferentes, então não é suficiente simplesmente habilitar Exchange arquivamento nas configurações de arquivamento; que não resultará em mensagens instantâneas e transcrições de webconferência sendo arquivadas em Exchange. Em vez disso, você também deve configurar a propriedade ExchangeArchivingPolicy em cada uma das contas de Skype for Business Server de usuário relevantes. Esta propriedade pode ser definida para uma dos quatro valores possíveis:

1. **Nãonitializado**. Indica que o arquivamento será baseado nas configurações de In-Place De espera configuradas para a caixa de correio de Exchange do usuário; se In-Place espera não tiver sido habilitada na caixa de correio do usuário, o usuário terá suas transcrições de mensagens e webconferências arquivadas em Skype for Business Server.

2. **UseLyncArchivingPolicy**. Indica que as transcrições de mensagens instantâneas e webconferências do usuário devem ser arquivadas Skype for Business Server em vez de Exchange.

3. **NoArchiving**. Indica que as transcrições de mensagem instantânea e conferência da Web do usuário não devem ser arquivadas. Observe que essa configuração substitui todas as Skype for Business Server de arquivamento atribuídas ao usuário.

4. **ArchivingToExchange**. Indica que as transcrições de mensagens instantâneas e webconferência do usuário devem ser arquivadas no Exchange independentemente das configurações de espera do In-Place que tenham (ou não) sido atribuídas à caixa de correio do usuário.

Por exemplo, para configurar uma conta de usuário para que as transcrições de mensagens instantâneas e webconferências sejam sempre arquivadas Exchange você pode usar um comando semelhante a este no Shell de Gerenciamento do Skype for Business Server:

```powershell
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

Se você deseja definir a mesma política de arquivamento para um grupo de usuários (por exemplo, todos os usuários hospedados em um pool do Registrador específico), é possível usar um comando semelhante ao seguinte:

```powershell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

Observe que você deve usar Skype for Business Server Shell de Gerenciamento (e Windows PowerShell) para configurar o valor da propriedade ExchangeArchivingPolicy. Essa propriedade não é exposta aos administradores no Skype for Business Server.

Se você deseja ver uma lista de todos os usuários atribuídos com uma política de arquivamento específica, é possível usar um comando semelhante ao seguinte, que retorna o nome de exibição do Active Directory de todos os usuários com a propriedade ExchangeArchivingPolicy definida para Não inicializado:

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

Da mesma forma, este comando retorna o nome de exibição dos usuários que não tem a propriedade ExchangeArchivingPolicy definida para UseLyncArchivingPolicy:

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```