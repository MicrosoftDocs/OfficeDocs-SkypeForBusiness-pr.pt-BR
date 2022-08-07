---
title: Configure a hierarquia de segmentação de sua equipe
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried, acolonna
search.appverid: MET150
description: Saiba como configurar uma hierarquia de equipe em sua organização para publicar conteúdo em um grande conjunto de equipes.
audience: admin
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: aa18168c9e8755a9b6b895ba48c38f8f79005177
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271076"
---
# <a name="set-up-your-team-targeting-hierarchy"></a>Configure a hierarquia de segmentação de sua equipe

Configurar uma hierarquia de direcionamento de equipe permitirá que sua organização publique conteúdo em um grande conjunto de equipes. A hierarquia de direcionamento de equipe define como todas as equipes em sua hierarquia estão relacionadas entre si, quais usuários podem publicar tarefas e em quais equipes os usuários têm permissões para publicar. Os recursos de publicação são desabilitados para todos os usuários, a menos que uma hierarquia de direcionamento de equipe esteja configurada para sua organização. Para configurar uma hierarquia de direcionamento de equipe, você precisará criar um arquivo que defina a hierarquia e, em seguida, carregá-lo no Teams para aplicá-lo à sua organização. Depois que o esquema é carregado, os aplicativos no Teams podem usá-lo.

> [!IMPORTANT]
> Para a versão inicial, somente o aplicativo Tarefas dá suporte a equipes hierárquicas.  Aplicar uma hierarquia de direcionamento de equipe à sua organização habilitará a publicação [de](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df) tarefas no aplicativo Tarefas. Você não verá uma hierarquia de equipes em outras áreas do Microsoft Teams.

Aqui está um exemplo de como a hierarquia é representada no aplicativo Tarefas no Teams. Depois que uma lista de tarefas é criada, os membros da equipe de publicação podem selecionar as equipes de destinatários para enviar (publicar) a lista de tarefas. Ao selecionar equipes, a equipe de publicação pode filtrar por hierarquia, por atributos ou uma combinação de ambos.<br>

![Captura de tela da publicação de tarefas.](media/manage-tasks-app-publish.png)

## <a name="terminology"></a>Terminologia

Os termos a seguir serão importantes à medida que você navegar pelas hierarquias. As equipes serão chamadas de **nós**.

* **Os nós raiz** são os nós mais principais na hierarquia. No exemplo, Retail Communications é um nó raiz.
* **Nós pai e** **nós filho são** termos que representam uma relação entre dois nós conectados. No exemplo, o Distrito 01 é um nó filho da Área 1.
* Vários níveis de filhos são chamados de **descendentes**. Os distritos 01, Store 01, Store 03, Store 07, District 02 e District 03 são todos descendentes da Área 1.
* Um nó sem filhos é chamado de **nó folha**. Eles estão na parte inferior de uma hierarquia.
* **As equipes** de destinatários são equipes que foram selecionadas para receber um conjunto específico de conteúdo a ser publicado. Eles devem ser nós folha.

## <a name="plan-your-hierarchy"></a>Planejar sua hierarquia

Antes de criar o esquema que define sua hierarquia, você precisa fazer algum planejamento e decidir como deseja moldar sua organização.  Uma das primeiras prioridades é decidir quais grupos organizacionais precisam publicar tarefas em outros grupos. Cada nó na hierarquia representa um grupo de trabalho ou grupo de grupos.

### <a name="permissions-to-publish"></a>Permissões para publicar

A permissão para publicar depende se um usuário é membro de qualquer equipe na hierarquia, além da relação dessa equipe ou conjunto de equipes com outras equipes na hierarquia.

> [!NOTE]
> O proprietário de uma equipe também recebe permissões de publicação.

* Se um usuário for membro de pelo menos uma equipe que tenha descendentes na hierarquia, esse usuário poderá publicar nesses descendentes sem ser membro de todas as equipes nas quais deseja publicar.
* Se um usuário for membro de pelo menos uma equipe na hierarquia, mas não for membro de nenhuma equipe com descendentes na hierarquia, esse usuário poderá ver e receber conteúdo publicado de sua organização.
* Se um usuário não for membro de nenhuma equipe na hierarquia, esse usuário não verá nenhuma funcionalidade relacionada à publicação.

### <a name="guidelines"></a>Diretrizes

* Só pode haver um arquivo de hierarquia aplicado por organização. No entanto, você pode incluir diferentes partes da sua organização juntas como hierarquias distintas de nós em um arquivo. Por exemplo, a Contoso Pharmaceuticals tem um nó raiz de Farmácia e um nó raiz de varejo. Ambos os nós raiz têm várias linhas de descendentes e não há sobreposição entre eles.
* Somente nós folha podem ser destinatários de uma publicação. Outros nós na hierarquia são úteis para selecionar destinatários de uma publicação.
* Uma equipe só pode ser representada uma vez em uma hierarquia.
* Uma hierarquia pode conter até 15.000 nós. Planejamos trabalhar com clientes para aumentar esse limite para organizações maiores.

### <a name="example-hierarchy"></a>Hierarquia de exemplo

Por exemplo, na hierarquia a seguir, Recall, Comunicações e RH podem publicar tarefas em cada nó inferior (equipe) na hierarquia, mas a Zona Nordeste só pode publicar tarefas nas equipes da New York Store e da Boston Store. A hierarquia de exemplo permite que os grupos de Recall, Comunicações e RH publiquem tarefas que se aplicam a toda a empresa, como informações de benefícios ou mensagens do CEO. A Zona Nordeste pode publicar tarefas como agendamento de pessoal, informações meteorológicas e assim por diante, somente para as equipes da Loja de Nova York e da Boston Store.

![Exemplo hierárquico de equipe.](media/team-targeting-schema-example-new.png)

## <a name="create-your-hierarchy"></a>Criar sua hierarquia

> [!NOTE]
> O restante deste artigo aborda a configuração de uma hierarquia de equipe no contexto de publicação de tarefas para as equipes de destinatário. Consulte Gerenciar [o aplicativo Tarefas para](./manage-tasks-app.md) sua organização no Teams para obter uma visão geral do aplicativo Tarefas, em que a publicação de tarefas aparece quando habilitada.

O esquema que define sua hierarquia é baseado em um arquivo CSV (valores separados por vírgula). O arquivo deve estar no formato UTF-8. Cada linha no arquivo CSV corresponde a um nó dentro da hierarquia de equipes. Cada linha contém informações que nomeia o nó dentro da hierarquia, opcionalmente o vincula a uma equipe e inclui atributos que podem ser usados para filtrar equipes em aplicativos que dão suporte a ela.

Você também pode definir **buckets**, que são categorias que a equipe de publicação pode usar para organizar o conteúdo enviado às equipes de destinatários para facilitar a exibição, classificação e foco no conteúdo relevante.

### <a name="add-required-columns"></a>Adicionar colunas necessárias

O arquivo CSV deve conter as três colunas a seguir, na ordem a seguir, começando na primeira coluna. Um nó deve ser vinculado a uma equipe para que ele receba tarefas.

| Nome da coluna   | Obrigatório | Descrição   |
----------------|----------|---------------|
| DisplayName    | Sim      | Esse campo é o nome do nó. O nome pode ter até 100 caracteres e conter apenas os caracteres A-Z, a-z e 0-9. Os nomes de nó devem ser exclusivos. |
| ParentName    | Sim       | Esse é o nome do nó pai. O valor especificado aqui deve corresponder exatamente ao valor no **campo DisplayName** do nó pai. Se você quiser adicionar mais de um nó pai, separe cada nome de nó pai com um ponto e vírgula (;). Você pode adicionar até 25 nós pai e cada nome de nó pai pode ter até 2500 caracteres. Um nó só poderá ter vários nós pai se os nós pai forem nós raiz.   <br><br>**IMPORTANTE** Tenha cuidado para não criar um loop em que um pai mais alto na hierarquia faz referência a um nó filho mais baixo na hierarquia. Não há suporte para isso. |
| TeamId        | Sim, se a equipe publicar tarefas ou receber tarefas de um nó pai       | Ele contém a ID da equipe à qual você deseja vincular um nó. Cada nó deve se referir a uma equipe exclusiva, portanto, cada valor de TeamId pode aparecer apenas uma vez no arquivo de hierarquia. Para obter a ID de uma equipe à qual você deseja vincular um nó, execute o seguinte comando do PowerShell: `Get-Team | Export-Csv TeamList.csv`. Esse comando lista as equipes em sua organização e inclui o nome e a ID de cada equipe. Localize o nome da equipe à qual você deseja vincular e copie a ID para esse campo.|

> [!NOTE]
> Se um nó não for um nó raiz ou um nó folha e você não precisar que a associação à equipe conceda as permissões correspondentes para publicação e relatório, você poderá deixar o TeamId em branco. Esse método pode ser usado para adicionar mais granularidade ao escolher equipes de destinatários ou para exibir relatórios de conclusão sem ter uma equipe correspondente.

### <a name="add-attribute-columns"></a>Adicionar colunas de atributo

Depois de adicionar as três colunas necessárias, você pode adicionar colunas de atributo opcionais. Esses atributos podem ser usados para filtrar nós para que você possa selecionar com mais facilidade aqueles nos quais deseja publicar tarefas. Há duas maneiras de definir seus atributos, dependendo se os valores para esse atributo são mutuamente exclusivos.

|Maneiras de adicionar atributos|Descrição |Exemplo  |
|---|---------|---------|
|Se os valores de um atributo forem mutuamente exclusivos, o nome da coluna que você especificar se tornará o nome do atributo.|Cada linha pode conter um valor para esse atributo, e cada coluna de atributo pode ter até 50 valores exclusivos. Cada valor pode ter até 100 caracteres. O conjunto de valores de atributo especificado na coluna de atributo será exibido como valores de filtro para esse atributo ao selecionar equipes de destinatário usando a hierarquia de direcionamento de equipe.|Você deseja que os usuários possam filtrar os repositórios por layout. Os valores para esse atributo são mutuamente exclusivos porque um repositório pode ter apenas um layout. <br><br>Para adicionar um atributo a repositórios de filtro por layout, adicione uma coluna chamada Layout da Loja. Neste exemplo, os valores para o atributo de layout da Loja são Compact, Standard e Large.
|Se você precisar indicar vários valores para um atributo e os valores não forem mutuamente exclusivos, use o formato **AttributeName:UniqueValue** para os nomes de coluna. <br><br>**IMPORTANTE** Certifique-se de usar os dois-pontos somente em inglês (:) como unicode não tem suporte como um delimitador de coluna de atributo. |A cadeia de caracteres de texto antes dos dois-pontos (:) torna-se o nome do atributo. Todas as colunas que contêm a mesma cadeia de caracteres de texto antes dos dois-pontos (:) são agrupados em uma seção no menu de filtragem. Cada uma das cadeias de caracteres após os dois-pontos se torna os valores dessa seção.<br><br>Cada linha pode ter um valor de 0 (zero) ou 1 para esse atributo. Um valor 0 significa que o atributo não se aplica ao nó e um valor de 1 significa que o atributo se aplica a esse nó.|Você deseja que os usuários possam filtrar os repositórios por departamento. Um repositório pode ter vários departamentos e, portanto, os valores para esse atributo não são mutuamente exclusivos.<br><br>Neste exemplo, adicionamos Departments:Clothing, Departments:Electronics, Departments:Foods, Departments:Home and Garden, Departments:Sport goods as attribute columns. Os departamentos se tornam o nome do atributo e os usuários podem filtrar pelos departamentos de Roupas, Eletrônicos, Alimentos, Casa e Jardim e Artigos Esportivos.|

Ao adicionar uma coluna de atributo, lembre-se do seguinte:

* O nome da coluna que você especificar ou o nome da coluna que você especificar antes dos dois-pontos (:) torna-se o nome do atributo. Esse valor será exibido nos aplicativos do Teams que usam a hierarquia.
* Você pode ter até 50 colunas de atributo em sua hierarquia.
* O nome da coluna pode ter até 100 caracteres e conter apenas os caracteres A-Z, a-z e 0-9 e espaços. Os nomes de coluna devem ser exclusivos.

### <a name="add-bucket-columns"></a>Adicionar colunas de bucket

Você pode adicionar colunas de bucket para criar buckets, que são agrupamentos nos quais as tarefas podem ser organizadas. Cada bucket obtém sua própria coluna no arquivo CSV. Os buckets criados são disponibilizados para a equipe de publicação. A equipe de publicação pode usar esses buckets para categorizar tarefas para as equipes de destinatário. Se um bucket ainda não existir em uma equipe, os buckets serão criados sob demanda quando as tarefas forem publicadas.

Ao categorizar os itens de trabalho uma vez centralmente, a equipe de publicação pode pré-organizar a lista de tarefas para todas as dezenas, centenas ou milhares de equipes de destinatários que recebem a lista de tarefas. As equipes de destinatários podem classificar e filtrar suas tarefas por bucket para se concentrar na área mais relevante para seu trabalho.

Ao adicionar uma coluna de bucket, observe o seguinte:

* O nome da coluna se torna o nome do bucket. Cada bucket especificado será exibido na lista Buckets nos aplicativos do Teams que usam a hierarquia.
* Recomendamos que você não inclua informações confidenciais em nomes de bucket. No momento, as equipes de publicação não podem remover um bucket por meio da publicação após sua criação.
* O nome da coluna deve ser precedido por uma hashtag (#). Ele pode ter até 100 caracteres e conter apenas os caracteres A-Z, a-z e 0-9. Por exemplo, #Operations e #Frozen bens.
* Uma hierarquia pode conter até 25 colunas de bucket. Planejamos trabalhar com clientes para aumentar esse limite para organizações maiores.

### <a name="example"></a>Exemplo

Aqui está um exemplo de um arquivo CSV de esquema que seria criado para dar suporte à hierarquia mostrada na imagem anterior. Esse esquema contém o seguinte:

* Três colunas necessárias chamadas `TargetName`, `ParentName`e `TeamId`
* Três colunas de atributo chamadas `Store layout`, `Departments:Clothing`e `Departments:Foods`
* Três colunas de bucket chamadas `Fresh Foods`, `Frozen Foods`e `Women's Wear`

O `Store layout` atributo tem valores que incluem `Compact`, `Standard`e `Large`. As `Departments` colunas de atributo podem ser definidas com um valor de `0` (zero) ou `1`. O `Store` layout e `Departments` os atributos não são mostrados na imagem acima. Eles são adicionados aqui para ajudar a mostrar como os atributos podem ser adicionados às entradas de nó. O mesmo é verdadeiro para as três colunas de bucket.

```CSV
TargetName,ParentName,TeamId,Store layout,Departments:Clothing,Departments:Foods,#Fresh Foods,#Frozen Foods,#Women's Wear
Recall,,db23e6ba-04a6-412a-95e8-49e5b01943ba,,,,,,
Communications,,145399ce-a761-4843-a110-3077249037fc,,,,,,
HR,,125399ce-a761-4983-a125-3abc249037fc,,,,,,
East Regional Office,HR;Communications;Recall,,,,,,,
West Regional Office,HR;Communications;Recall,,,,,,,
Northeast Zone,East Regional Office,,,,,,,
Southeast Zone,East Regional Office,,,,,,,
New York Store,Northeast Zone,e2ba65f6-25e7-488b-b8f0-b8562d5de60a,Large,1,1,,,
Boston Store,Northeast Zone,0454f08a-0507-437c-969a-682eb2fae7fc,Standard,1,1,,,
Miami Store,Southeast Zone,619d6e4e-5f68-4b36-8e1f-16c98d7396c1,Compact,0,1,,,
New Orleans Store,Southeast Zone,6be960b8-72af-4561-a343-9ac4711874eb,Compact,0,1,,,
Seattle Store,West Regional Zone,487c0d20-4e55-4dc2-8187-a24c826e0fee,Standard,1,1,,,
Los Angeles Store,West Regional Zone,204a1287-2efb-4a8a-88e0-56fbaf5a2389,Large,1,1,,,
```

## <a name="apply-your-hierarchy"></a>Aplicar sua hierarquia

> [!NOTE] 
> Para executar essa etapa, você deve instalar e usar o módulo de visualização pública do PowerShell do Teams Galeria do PowerShell. Para obter etapas sobre como instalar o módulo, consulte Instalar o PowerShell do Teams.

> [!NOTE]
> Os clientes do GCC (Government Community Cloud) devem usar a [versão prévia do cmdlet versão 2.4.0 ou](https://www.powershellgallery.com/packages/MicrosoftTeams/2.4.0-preview) posterior para garantir que os dados sejam roteados para o ambiente GCC, em vez do ambiente de nuvem pública.

Depois de definir sua hierarquia no arquivo CSV do esquema, você estará pronto para carregá-la no Teams. Para fazer isso, execute o comando a seguir. Você deve ser um administrador global ou administrador de serviços do Teams para executar esta etapa.

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

### <a name="update-your-hierarchy"></a>Atualizar sua hierarquia

Você pode carregar uma nova hierarquia para substituir a antiga usando o mesmo comando do PowerShell acima. Cada vez que você carrega uma nova hierarquia, ela substitui a hierarquia anterior.

### <a name="check-the-status-of-your-hierarchy"></a>Verificar o status da hierarquia

Você pode executar o comando a seguir para verificar o status do upload da hierarquia.

```powershell
Get-TeamTargetingHierarchyStatus
```

O comando retornará os seguintes campos:

Campo|Descrição
-----|------------
Id | A ID exclusiva para o upload.
Status | Status do upload. Os valores **incluem Iniciando**, **Validando**, **Bem-sucedido** e **Com Falha**
ErrorDetails | Detalhes se houver um erro de upload. Para obter mais informações sobre os detalhes do erro, consulte a seção Solução de problemas. Se não houver nenhum erro, esse campo estará em branco.
LastUpdatedAt | Carimbo de data/hora e data de quando o arquivo foi atualizado pela última vez.
LastModifiedBy | A ID do último usuário que modificou o arquivo.
FileName | O nome do arquivo do CSV.

## <a name="remove-your-hierarchy"></a>Remover sua hierarquia

Se você quiser desabilitar imediatamente a **guia Listas publicadas** para todos os usuários em sua organização, poderá remover sua hierarquia. Os usuários não terão acesso à guia Listas **publicadas** ou a nenhuma das funcionalidades na guia.  Isso inclui a capacidade de criar novas listas de tarefas para publicar, acessar listas de rascunho, publicar, cancelar publicação e duplicar listas e exibir relatórios. Remover a hierarquia não cancela a publicação de tarefas que foram publicadas anteriormente. Essas tarefas permanecerão disponíveis para que as equipes de destinatários sejam concluídas.

Para remover sua hierarquia, execute o comando a seguir. Você deve ser um administrador para executar esta etapa.

```powershell
Remove-TeamTargetingHierarchy
```

Ao confirmar a exclusão, a mensagem de status ainda exibirá que o esquema anterior está presente, embora a tentativa de excluir novamente retorne um erro de que o objeto é nulo.

## <a name="create-a-sample-hierarchy"></a>Criar uma hierarquia de exemplo

### <a name="install-the-teams-powershell-module"></a>Instalar o módulo do PowerShell do Teams

> [!IMPORTANT]
> Para executar essa etapa, você deve instalar e usar o módulo de visualização pública do PowerShell do [Teams Galeria do PowerShell.](https://www.powershellgallery.com/packages/MicrosoftTeams/) Para obter etapas sobre como instalar o módulo, consulte [Instalar o PowerShell do Teams](teams-powershell-install.md).

### <a name="sample-script"></a>Script de exemplo

O script a seguir pode ser usado para criar as equipes e carregar um arquivo .csv para seu locatário do Microsoft Teams. Se você tiver uma hierarquia existente, esse script a substituirá.

#### <a name="create-teams-for-a-simple-hierarchy"></a>Criar equipes para uma hierarquia simples

```powershell
$tm1 = New-Team -DisplayName "HQ"
$tm2 = New-Team -DisplayName "North"
$tm3 = New-Team -DisplayName "Store 1"
$tm4 = New-Team -DisplayName "Store 2"
$tm5 = New-Team -DisplayName "South"
$tm6 = New-Team -DisplayName "Store 3"
$tm7 = New-Team -DisplayName "Store 4"
```

#### <a name="use-team-data-to-create-comma-separated-output-displayname-parentname-teamid"></a>Usar dados de equipe para criar uma saída separada por vírgulas (DisplayName, ParentName, TeamId)

```powershell
$csvOutput = "DisplayName" + "," + "ParentName" + "," + "TeamId" + "`n"
$csvOutput = $csvOutput + $tm1.DisplayName + "," + "," + $tm1.GroupID + "`n"
$csvOutput = $csvOutput + $tm2.DisplayName + "," + $tm1.DisplayName + "," + $tm2.GroupID + "`n"
$csvOutput = $csvOutput + $tm3.DisplayName + "," + $tm2.DisplayName + "," + $tm3.GroupID + "`n"
$csvOutput = $csvOutput + $tm4.DisplayName + "," + $tm2.DisplayName + "," + $tm4.GroupID + "`n"
$csvOutput = $csvOutput + $tm5.DisplayName + "," + $tm1.DisplayName + "," + $tm5.GroupID + "`n"
$csvOutput = $csvOutput + $tm6.DisplayName + "," + $tm5.DisplayName + "," + $tm6.GroupID + "`n"
$csvOutput = $csvOutput + $tm7.DisplayName + "," + $tm5.DisplayName + "," + $tm7.GroupID 
```

#### <a name="save-output-to-a-csv-file-in-the-downloads-folder"></a>Salvar a saída em um .csv na pasta **Downloads**

```powershell
$csvOutputPath = $env:USERPROFILE + "\downloads\testhierarchy-" + (Get-Date -Format "yyyy-MM-dd-hhmmss") + ".csv" 
$csvOutput | Out-File $csvOutputPath
```

#### <a name="upload-the-hierarchy"></a>Carregar a hierarquia

```powershell
Set-TeamTargetingHierarchy -FilePath $csvOutputPath
Get-TeamTargetingHierarchyStatus
```

## <a name="troubleshooting"></a>Solução de problemas

### <a name="how-to-view-error-details"></a>Como exibir detalhes do erro

Você pode executar o comando a seguir para entender o que está causando um erro e retornar os detalhes do erro.

```powershell
(Get-TeamTargetingHierarchyStatus).ErrorDetails.ErrorMessage
```

### <a name="you-receive-an-error-message-when-you-upload-your-schema-csv-file"></a>Você recebe uma mensagem de erro ao carregar o arquivo CSV do esquema

Anote a mensagem de erro, pois ela deve incluir informações de solução de problemas para indicar por que o esquema não pôde ser carregado. Examine e edite o arquivo CSV do esquema com base nas informações na mensagem de erro e tente novamente.

### <a name="you-receive-an-error-invalidteamid-error-message-when-you-upload-your-schema-csv-file"></a>Você recebe uma mensagem de erro "Erro: InvalidTeamId" ao carregar o arquivo CSV do esquema

Ao tentar carregar o arquivo CSV do esquema, você receberá a seguinte mensagem de erro:

```console
Error: InvalidTeamId
Description: TeamID in row # doesn't match a valid Group ID. Please view our documentation to learn how to get the proper GroupID for each team.
```

Verifique se você está usando o TeamId correto para a equipe no arquivo CSV do esquema. O TeamId deve ser o mesmo que a ID de Grupo do grupo do Microsoft 365 que faz backup da equipe. Você pode pesquisar a ID do Grupo da equipe no Centro de administração do Microsoft Teams.

1. No painel de navegação esquerdo do centro [de administração do Microsoft Teams](https://admin.teams.microsoft.com/), acesse **Teams** > **Manage teams**.
2. Se **a coluna ID do** Grupo não for exibida na tabela, selecione Editar **colunas** no canto superior direito da tabela e, em seguida, ative a **ID do Grupo**.
3. Localize a equipe na lista e localize a ID do Grupo.

Verifique se a TeamId no arquivo CSV do esquema corresponde à ID do Grupo exibida no centro de administração do Microsoft Teams.

## <a name="related-topics"></a>Tópicos relacionados

* [Gerenciar o aplicativo Tarefas para sua organização no Teams](manage-tasks-app.md)
* [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
