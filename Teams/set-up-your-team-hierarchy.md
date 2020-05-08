---
title: Configurar sua hierarquia de direcionamento de equipe
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried
search.appverid: MET150
description: Saiba como configurar uma hierarquia de equipe em sua organização para publicar conteúdo em um grande conjunto de Teams.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2bb8133733f7230715753ecea0118fc635af446b
ms.sourcegitcommit: 6e24ea8aa9cccf8a1a964c8ed414ef5c7de3dc17
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2020
ms.locfileid: "44158998"
---
# <a name="set-up-your-team-targeting-hierarchy"></a>Configurar sua hierarquia de direcionamento de equipe

> **No momento, este recurso está em visualização particular.**

Para criar uma hierarquia de equipes que podem ser usadas por sua organização para publicar conteúdo em um grande conjunto de equipes, você precisa configurar o esquema de direcionamento de equipe. O esquema define como todas as equipes em sua hierarquia estão relacionadas umas às outras e os atributos que podem ser usados para filtrar suas equipes. Depois de criar o esquema, carregue-o para o Microsoft Teams e a hierarquia será aplicada em toda a organização. Após o carregamento do esquema, os aplicativos dentro do cliente das equipes podem usá-lo. 

> [!IMPORTANT]
> Você não verá uma hierarquia de equipes quando estiver navegando em equipes ou canais dentro delas. Para ver a hierarquia do Teams, você precisa usar um aplicativo compatível com ele. Para a versão inicial, somente o aplicativo tarefas dá suporte a equipes hierárquicas. O restante deste artigo aborda a configuração de uma hierarquia de equipe no contexto de publicar tarefas em equipes de destinatários. Antes de configurar sua hierarquia de direcionamento de equipe, consulte [gerenciar o aplicativo tarefas para sua organização no Teams](manage-tasks-app.md) para obter uma visão geral da publicação de tarefas.

Veja um exemplo de como a hierarquia é representada no aplicativo tarefas no Microsoft Teams. Após a criação de uma lista de tarefas, os membros da equipe de publicação poderão selecionar as equipes de destinatários para enviar (publicar) a lista de tarefas. Ao selecionar o Microsoft Teams, a equipe de publicação pode filtrar por hierarquia, por atributos ou por uma combinação de ambos.<br>

![Captura de tela da publicação de tarefas](media/manage-tasks-app-publish.png)

## <a name="plan-your-hierarchy"></a>Planejar sua hierarquia

Antes de criar o esquema que define sua hierarquia, você precisa fazer alguns planejamentos e decidir como deseja fazer a forma de sua organização. Isso inclui decidir quais grupos organizacionais precisam publicar tarefas para outros grupos. Cada nó na hierarquia representa um grupo de trabalho ou grupo de grupos. Os nós na parte inferior da hierarquia (aqueles sem filhos) são equipes que podem receber tarefas enquanto outros nós (pais) são grupos organizacionais com permissão para publicar tarefas para baixo. Uma equipe só pode ser representada uma vez na hierarquia.

Por exemplo, na hierarquia a seguir, a cancelamento, as comunicações de varejo e a RH podem publicar tarefas em todos os nós inferiores (equipe) na hierarquia, enquanto a zona norte do Norte somente pode publicar tarefas para o loja de Nova York e para as equipes da loja de Boston. Essa hierarquia permite a cancelamento, a comunicação de revenda e os grupos de RH para publicar tarefas que se aplicam a toda a empresa, como informações de benefícios ou mensagens do CEO. A zona norte leste pode publicar tarefas, como agendamento de pessoal, informações de clima e assim por diante, somente para as equipes de loja de Nova York e loja de Boston.

![Exemplo de hierarquia de equipe](media/team-targeting-schema-example.png)

## <a name="create-your-hierarchy"></a>Criar sua hierarquia

O esquema que define sua hierarquia é baseado em um arquivo de valores separados por vírgula (CSV). Cada linha no arquivo CSV corresponde a um nó dentro da hierarquia de Teams. Cada linha contém informações que nomeiam o nó dentro da hierarquia, opcionalmente, vincula-o a uma equipe e inclui atributos que podem ser usados para filtrar equipes em aplicativos que o dão suporte a ele.

Você também pode definir buckets, que são categorias que a equipe de publicação pode usar para organizar o conteúdo enviado às equipes de destinatários para facilitar a visualização, a classificação e o foco no conteúdo relevante.

### <a name="add-required-columns"></a>Adicionar colunas obrigatórias

O arquivo CSV deve conter as três colunas a seguir, na seguinte ordem, começando na primeira coluna. Um nó deve ser vinculado a uma equipe para que ele receba tarefas. Durante a visualização particular, damos suporte a nós 500. Na inicialização, esperamos dar suporte a pelo menos nós do 2.000 por padrão. Planejamos trabalhar com clientes para gerar esse limite para organizações maiores.

| Nome da coluna   | Obrigatório | Descrição   |
----------------|----------|---------------|
| TargetName    | Sim      | Este é o nome do nó. O nome pode ter até 100 caracteres de comprimento e conter apenas os caracteres A-Z, a-z e 0-9. Os nomes de nó devem ser exclusivos. |
| ParentName    | Sim       | Este é o nome do nó pai. O valor que você especifica aqui deve coincidir com o valor no campo TargetName do nó pai exatamente. Se você quiser adicionar mais de um nó pai, separe cada nome de nó pai com um ponto-e-vírgula (;). Você pode adicionar até 25 nós pai, e cada nome de nó pai pode ter até 2500 caracteres de comprimento. Um nó pode ter vários nós pai apenas se os nós pai são nós raiz.   <br><br>**Importante** Tenha cuidado para não criar um loop em que um pai mais alto na hierarquia faça referência a um nó filho inferior na hierarquia. Não há suporte para isso. |
| TeamID        | Sim, se a equipe publicar tarefas ou receber tarefas de um nó pai       | Isso contém a ID da equipe à qual você deseja vincular um nó. Um nó deve ser vinculado a uma equipe se estiver na parte inferior da sua hierarquia, se você quiser que os usuários possam publicar desse nó ou se quiser que os usuários possam ver relatórios para esse nó e seus descendentes. Por exemplo, se o seu gerente da região oeste do Office quiser ver o relatório de conclusão de tarefas para os nós que pertencem a essa região.<br><br>Se quiser adicionar um nó somente para fins de agrupamento de outros nós na hierarquia, você não precisará vincular esse nó a uma equipe e deixar este campo em branco. Você pode vincular cada nó a apenas uma equipe.<br>Para obter a ID de uma equipe à qual você deseja vincular um nó, execute o seguinte comando do PowerShell `Get-Team | Export-Csv TeamList.csv`:. Isso lista as equipes em sua organização e inclui o nome e a ID de cada equipe. Localize o nome da equipe à qual você deseja se vincular e copie a ID nesse campo.|

### <a name="add-attribute-columns"></a>Adicionar colunas de atributo

Depois de adicionar as três colunas obrigatórias, você pode adicionar colunas de atributo opcionais. Esses atributos podem ser usados para filtrar nós para que você possa selecionar facilmente os que deseja publicar tarefas. Há duas maneiras de definir seus atributos, dependendo se valores desse atributo são mutuamente exclusivos.

|Maneiras de adicionar atributos|Descrição |Exemplo  |
|---|---------|---------|
|Se os valores de um atributo forem mutuamente exclusivos, o nome da coluna especificado torna-se o nome do atributo.|Cada linha pode conter um valor para esse atributo, e cada valor pode ter até 100 caracteres de comprimento. O conjunto de valores de atributo que você especificar na coluna Attribute será exibido como valores de filtro disponíveis para esse atributo em aplicativos Teams que usam a hierarquia. Cada coluna de atributo pode ter até 50 valores exclusivos. |Você deseja que os usuários possam filtrar as lojas por layout. Os valores para esse atributo são mutuamente exclusivos porque um repositório pode ter apenas um layout. <br><br>Para adicionar um atributo para filtrar lojas por layout, adicione uma coluna chamada layout da loja. Neste exemplo, os valores para o atributo de layout da loja são compacto, padrão e grande.
|Se você precisar indicar vários valores para um atributo e os valores não forem mutuamente exclusivos, use o formato **AttributeName: uniquevalue** para os nomes das colunas. |A cadeia de caracteres de texto antes dos dois pontos (:) torna-se o nome do atributo. Todas as colunas que contêm a mesma cadeia de texto antes dos dois pontos (:) são agrupados em uma seção no menu filtragem. Cada uma das cadeias de caracteres após os dois pontos se tornam os valores dessa seção.<br><br>Cada linha pode ter um valor de 0 (zero) ou 1 para esse atributo. Um valor 0 significa que o atributo não se aplica ao nó e um valor 1 significa que o atributo se aplica a esse nó.|Você deseja que os usuários possam filtrar lojas por departamento. Uma loja pode ter vários departamentos e, portanto, os valores desse atributo não são mutuamente exclusivos.<br><br>Neste exemplo, adicionamos departamentos: roupas, departamentos: eletrônicos, departamentos: alimentos, departamentos: casa e jardim, departamentos: bens esportivos como colunas de atributo. Os departamentos se tornam o nome do atributo e os usuários podem filtrar pelas roupas, eletrônicos, alimentos, casa e jardim e departamentos de artigos esportivos.|

Ao adicionar uma coluna de atributo, tenha em mente o seguinte:

- O nome da coluna que você especificar ou o nome da coluna especificado antes dos dois pontos (:) torna-se o nome do atributo. Esse valor será exibido nos aplicativos Teams que usam a hierarquia.
- O nome da coluna pode ter até 100 caracteres de comprimento e conter apenas os caracteres A-Z, a-z e 0-9 e espaços. Os nomes de coluna devem ser exclusivos.
- No lançamento, pretendemos permitir colunas de atributo do 50.

### <a name="add-bucket-columns"></a>Adicionar colunas de Bucket

Você pode adicionar colunas de Bucket para criar buckets, que são agrupamentos em quais tarefas podem ser organizadas. Cada bucket obtém sua própria coluna no arquivo CSV. Os buckets que você cria são disponibilizados para a equipe de publicação. A equipe de publicação poderá usar esses buckets para categorizar tarefas para as equipes do destinatário. Se um Bucket ainda não existir em uma equipe, os buckets são criados sob demanda quando as tarefas são publicadas.

Ao categorizar o trabalho uma vez centralmente, a equipe de publicação pode organizar a lista de tarefas para todas as dezenas, centenas ou milhares de equipes de destinatários que recebem a lista de tarefas. Em seguida, as equipes do destinatário podem classificar e filtrar suas tarefas por Bucket para se concentrar na área mais relevante para o trabalho.

Ao adicionar uma coluna de Bucket, observe o seguinte:

- O nome da coluna se torna o nome do Bucket. Cada bucket que você especificar aparecerá na lista buckets nos aplicativos Teams que usam a hierarquia. Recomendamos que você não inclua informações confidenciais em nomes de Bucket. Neste momento, o Microsoft Teams não pode remover um Bucket por meio da publicação após sua criação.
- O nome da coluna deve ser precedido por um hashtag (#). Pode ter até 100 caracteres de comprimento e conter apenas os caracteres A-Z, a-z e 0-9. Por exemplo, #Operations e #Frozen bens.
- No lançamento, esperamos dar suporte a 25 colunas de Bucket. Planejamos trabalhar com clientes para aumentar esse limite para organizações maiores.

### <a name="example"></a>Exemplo

Aqui está um exemplo de um arquivo CSV de esquema que seria criado para dar suporte à hierarquia mostrada na imagem acima. Este esquema contém o seguinte:

- Três colunas obrigatórias `TargetName`nomeadas, `ParentName`e`TeamID`
- Três colunas de atributo `Store layout`chamadas `Departments:Clothing`, e`Departments:Foods`
- Três colunas de Bucket `Fresh Foods`chamadas `Frozen Foods`, e`Womenswear`

O `Store layout` atributo tem valores que incluem `Compact`, `Standard`e `Large`. As `Departments` colunas de atributo podem ser definidas com um valor `0` de (zero) `1`ou. O `Store` layout e `Departments` os atributos não são mostrados na imagem acima. Elas são adicionadas aqui para ajudar a mostrar como os atributos podem ser adicionados às entradas de nó. O mesmo se aplica às colunas de três buckets.


| TargetName             | ParentName                      | TeamID                       | Layout da loja|Departamentos: roupas|Departamentos: alimentos|#Fresh alimentos|#Frozen alimentos|#Womenswear|
|------------------------|-------------------------|--------------------------------------|-------------|---|---|---|---|---|
| Esqueça                 |                         | db23e6ba-04a6-412a-95e8-49e5b01943ba |||||||
| Comunicações         |                         | 145399ce-a761-4843-a110-3077249037fc |||||||
| RH                     |                         | b8f7db91-201c-4cf9-9f7e-90a4894ed8e4 |||||||
| Escritório regional da Ásia   |                         |                                      |||||||
| Escritório regional da região oeste   |                         |                                      |||||||
| Zona norte leste        | Escritório regional da Ásia    |                                      |||||||
| Zona sul leste        | Escritório regional da Ásia    |                                      |||||||
| Loja de Nova York         | Zona norte leste         | e2ba65f6-25e7-488b-b8f0-b8562d5de60a |Grande|1|1||||
| Loja de Boston           | Zona norte leste         | 0454f08a-0507-437c-969a-682eb2fae7fc |Standard|1|1||||
| Loja de Miami            | Zona sul leste         | 619d6e4e-5f68-4b36-8e1f-16c98d7396c1 |Reduzido|0|1||||
| Nova loja Orleans      | Zona sul leste         | 6be960b8-72af-4561-a343-9ac4711874eb |Reduzido|0|1||||
| Loja de Seattle          | Escritório regional da região oeste    | 487c0d20-4e55-4dc2-8187-a24c826e0fee |Standard|1|1||||
| Loja de Los Angeles      | Escritório regional da região oeste    | 204a1287-2efb-4a8a-88e0-56fbaf5a2389 |Grande|1|1||||

## <a name="apply-your-hierarchy"></a>Aplicar sua hierarquia

> [!IMPORTANT]
> Para executar esta etapa, você deve instalar e usar a versão mais recente do módulo do teams PowerShell a partir da Galeria de teste do PowerShell. Para ver as etapas sobre como fazer isso, confira [instalar o módulo PowerShell do teams mais recente na Galeria de teste do PowerShell](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery).

Depois de definir sua hierarquia no arquivo CSV de esquema, você estará pronto para carregá-la para o Microsoft Teams. Para fazer isso, execute o seguinte comando. Você deve ser administrador global ou administrador do teams Service para executar esta etapa.

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

## <a name="remove-your-hierarchy"></a>Remover sua hierarquia

> [!IMPORTANT]
> Para executar esta etapa, você deve instalar e usar a versão mais recente do módulo do teams PowerShell a partir da Galeria de teste do PowerShell. Para ver as etapas sobre como fazer isso, confira [instalar o módulo PowerShell do teams mais recente na Galeria de teste do PowerShell](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery).

Se quiser desabilitar imediatamente a guia **listas publicadas** para todos os usuários de sua organização, você poderá remover sua hierarquia. Os usuários não terão acesso à guia **listas publicadas** ou a qualquer uma das funcionalidades na guia.  Isso inclui a capacidade de criar novas listas de tarefas para publicar, acessar listas de rascunhos, publicar, cancelar a publicação e listas duplicadas e exibir relatórios. A remoção da hierarquia não publica tarefas que foram publicadas anteriormente. Essas tarefas permanecerão disponíveis para que as equipes de destinatário sejam concluídas. 

Para remover sua hierarquia, execute o seguinte comando. Você deve ser um administrador para executar esta etapa. 

```powershell
Remove-TeamTargetingHierarchy
```

### <a name="teams-powershell-module"></a>Módulo do teams PowerShell

#### <a name="install-the-latest-teams-powershell-module-from-the-powershell-test-gallery"></a>Instalar o módulo do PowerShell do teams mais recente na Galeria de teste do PowerShell

A versão mais recente disponível publicamente do módulo Teams PowerShell (atualmente [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5)) não oferece suporte ao gerenciamento da hierarquia da equipe. Use estas etapas para instalar a versão mais recente do módulo do teams PowerShell com suporte à hierarquia da equipe, na Galeria de teste do PowerShell.

> [!NOTE]
> Não instale o módulo Teams PowerShell da Galeria de teste do PowerShell lado a lado com uma versão do módulo da Galeria pública do PowerShell. Siga estas etapas para desinstalar primeiro o módulo do teams PowerShell da galeria do PowerShell público e instalar a versão mais recente do módulo da Galeria de teste do PowerShell.

1. Feche todas as sessões existentes do PowerShell.
2. Inicie uma nova instância do módulo do Windows PowerShell.
3. Execute o seguinte para desinstalar o módulo do teams PowerShell da galeria do PowerShell público:

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. Feche todas as sessões existentes do PowerShell.
5. Inicie o módulo do Windows PowerShell novamente e, em seguida, execute o seguinte para registrar a Galeria de teste do PowerShell como uma fonte confiável:

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. Execute o seguinte para instalar o módulo do PowerShell mais recente do teams a partir da Galeria de teste do PowerShell:

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. Execute o seguinte para verificar se a versão mais recente do módulo do teams PowerShell da Galeria de teste do PowerShell foi instalada com êxito:

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a>Atualize para a versão mais recente do módulo do teams PowerShell da Galeria de teste do PowerShell

Se você já tiver instalado o módulo do teams PowerShell da Galeria de teste do PowerShell, use as etapas a seguir para atualizar para a versão mais recente.

1. Feche todas as sessões existentes do PowerShell.
2. Inicie uma nova instância do módulo do Windows PowerShell.
3. Execute o seguinte para atualizar a versão atualmente instalada do módulo do teams PowerShell a partir da Galeria de teste do PowerShell:

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. Execute o seguinte para verificar se a versão mais recente do módulo do teams PowerShell da Galeria de teste do PowerShell foi instalada com êxito:

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="troubleshooting"></a>Solução de problemas

### <a name="you-receive-an-error-message-when-you-upload-your-schema-file"></a>Você recebe uma mensagem de erro quando carrega o arquivo de esquema

Anote a mensagem de erro, pois ela deve incluir informações de solução de problemas para indicar por que o esquema não foi carregado. Revise e edite o arquivo CSV de esquema com base nas informações na mensagem de erro e tente novamente.

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar o aplicativo tarefas para sua organização no Teams](manage-tasks-app.md)
