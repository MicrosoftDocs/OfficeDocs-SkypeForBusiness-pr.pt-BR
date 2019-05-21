---
title: Implantar painel de qualidade de chamada no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 'Resumo: Saiba mais sobre o processo de implantação do painel de qualidade de chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 3cc3b81180453454f8615d31f57911c0958553c5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274839"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a>Implantar painel de qualidade de chamada no Skype for Business Server
 
**Resumo:** Saiba mais sobre o processo de implantação do painel de qualidade de chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.
  
## <a name="deployment-overview"></a>Visão geral da implantação

O painel de qualidade de chamada (CQD) consiste em três componentes principais:
  
- **Arquivar banco**de dados, em que os dados de qualidade da experiência (QoE) são duplicados e armazenados.
    
- **Cubo**, em que os dados do banco de dados de arquivo QoE são agregados para acesso otimizado e rápido.
    
- **Portal**, em que os usuários podem facilmente consultar e Visualizar dados de QoE.
    
![Componentes do CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
O processo de configuração para o arquivo de QoE envolve a criação do banco de dados de sistema de QoE, a implantação de um procedimento armazenado do SQL Server que moverá os dados do banco de dados de métricas de QoE de origem para o banco de dados de arquivo de distribuição e a configuração do trabalho do agente do SQL Server para executar o armazenamento procedimento em um intervalo regular. 
  
A implantação de cubo Obtém informações do usuário em que o arquivo de QoE está localizado, implanta o cubo e configura um trabalho normal do SQL Server Agent que irá atualizar o cubo em um intervalo regular.
  
A instalação do portal cria um banco de dados de repositório que armazena o mapeamento de usuários do CQD para os relatórios/consultas de cada usuário. Em seguida, ele configura um aplicativo Web do IIS que é o painel em que os usuários podem ver um conjunto de relatórios predefinido, bem como personalizar e criar suas próprias consultas para visualizar dados do cubo. A instalação do portal cria dois aplicativos Web adicionais que expõe APIs para que os usuários acessem programaticamente o repositório e o cubo. (Essas APIs também são usadas internamente pelo painel.)
  

|**Fase**|**Etapas**|**Funções e associação de grupo**|**Documentação**|
|:-----|:-----|:-----|:-----|
|Instale o hardware e o software obrigatórios.  <br/> |Decida sobre a configuração do CQD e escolha um SQL Server do qual executar a instalação.  <br/> |Usuário do domínio que é membro do grupo local de administradores.  <br/> |Seção "requisitos de pré-instalação" na documentação de implantação.  <br/> |
|Instale o CQD.  <br/> |Execute o MSI após o documento de implantação.  <br/> |Para executar a configuração, a conta de instalação deve ser um usuário de domínio que seja membro do grupo Administradores local e ter acesso de leitura ao banco de dados de métricas de QoE no servidor de monitoramento.  <br/> |Seções "contas e etapas de implantação" na documentação de implantação.  <br/> |
|Conceder acesso ao usuário.  <br/> |Para gerenciar a autorização do usuário para o portal, recomendamos usar a autorização de URL, que foi introduzida no IIS 7,0. Para obter mais informações, consulte [noções básicas sobre a autorização de URL do IIS 7,0](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).  <br/> |Usuário do domínio que é membro do grupo local de administradores.  <br/> |Gerenciando o acesso do usuário para a seção do portal na documentação de implantação.  <br/> |
|Opcional: forneça informações de mapeamento de sub-rede.  <br/> |Preencha as tabelas de mapeamento de rede e construção no banco de dados de arquivo QoE.  <br/> |Uma conta com acesso de gravação ao banco de dados de arquivo QoE.  <br/> |Seção "fornecendo informações de sub-rede" na documentação do usuário.  <br/> |
   


A implantação do painel de qualidade da chamada envolve a configuração da infraestrutura e a instalação do software. O procedimento a seguir descreve o processo.
  
## <a name="deployment-steps"></a>Etapas de implantação

1. Copie o CallQualityDashboard. msi para a máquina onde o componente de banco de dados de arquivo do CQD deve ser instalado (esse é o computador que tem o SQL Server instalado). 
    
2. Execute o MSI (o Windows solicitará que o privilégio de administrador seja executado). 
    
3. Aceite o EULA.
    
4. Selecione a pasta de destino na qual os arquivos relacionados a componentes de painel de qualidade de chamada serão localizados ou aceitará o local padrão.
    
5. Selecione todos os recursos.
    
6. Na página de configuração de arquivo de QoE, forneça as seguintes informações:
    
   - **Métricas de QoE SQL Server:** Nome da instância do SQL Server para a qual o BD métricas de QoE está localizado (essa será a fonte de dados).
    
   - **Arquivo de QoE nome do SQL Server:** Este é um campo somente leitura e foi corrigido para o nome de domínio totalmente qualificado do computador local. O arquivo morto DB só pode ser instalado no computador local.
    
   - **Instância de arquivo de QoE do SQL Server:** Um nome de instância local do SQL Server para o qual o BD de arquivo deve ser criado. Para usar uma instância padrão do SQL Server, deixe este campo em branco. Para usar uma instância nomeada do SQL Server, especifique o nome da instância (por exemplo, o nome\"após ").
    
   - **Banco de dados de QoE Archive:** Por padrão, essa opção é definida como "criar novo banco de dados". Como não há suporte para a atualização do banco de dados morto, a única circunstância sob a qual a opção "usar banco de dados existente" pode ser usada é se o banco de dados de arquivo morto existente tiver o mesmo esquema que a compilação a ser instalada.
    
   - **Diretório de arquivos do banco de dados:** Caminho para onde os arquivos de banco de dados (. MDF e. ldf) para o banco de dados de arquivo morto devem ser colocados. Isso deve estar em uma unidade (HDD2 na configuração de hardware recomendada) separada do sistema operacional. Observe que, como os nomes de arquivo são corrigidos na instalação, para evitar possíveis conflitos, é recomendável que um diretório em branco sem arquivos seja usado.
    
   - **Use várias partições:** O padrão é definido como "Multiple Partition", que exige Business Intelligence Edition ou Enterprise Edition do SQL Server. Para a edição Standard, selecione a opção "partição simples". Observe que o desempenho do processamento de cubo pode ser afetado se uma única partição for usada.
    
     > [!NOTE]
     > A opção seleção para usar várias partições não pode ser alterada após a conclusão da instalação. Para alterá-lo, o recurso de cubo precisa ser desinstalado primeiro e reinstalado usando-se a opção "alterar" no painel de controle. 
  
   - **Diretório de arquivos da partição:** Caminho para o local onde as partições para o banco de dados de arquivo QoE devem ser colocadas. Isso deve estar em uma unidade (HDD3 na configuração de hardware recomendada) separada da unidade do sistema operacional e da unidade de arquivos de log do banco de dados SQL. Observe que, como os nomes de arquivo são corrigidos na instalação, para evitar possíveis conflitos, é recomendável que um diretório em branco sem arquivos seja usado.
    
   - **Nome &amp; de usuário do trabalho do agente SQL: senha:** Nome e senha da conta de serviço de domínio (mascarado) que serão usados para executar a etapa "QoE Archive Data" do trabalho do SQL Server Agent (que executará o procedimento armazenado para buscar dados do BD de métricas de QoE em banco de dados de arquivo, portanto, essa conta deve ter acesso de leitura ao BD de métricas de QoE,  conforme indicado na seção contas. Essa conta também precisa ter um login na instância de arquivo QoE do SQL Server.
    
     > [!NOTE]
     > A conta em que a instância do SQL Server está sendo executada, como NT SERVICE\MSSQLSERVER, deve ter acesso/permissão aos diretórios acima para que a instalação seja bem-sucedida. Para obter detalhes, consulte [configurar permissões do sistema de arquivos para acesso ao mecanismo de banco de dados](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)
  
7. Ao clicar em avançar, o instalador executará verificações pré-requisitos e reportará se algum problema for encontrado. Quando as verificações de pré-requisito passarem, o instalador vai para a página de configuração de cubo. 
    
    > [!NOTE]
    > Se o instalador mostrar uma mensagem de aviso informando que o serviço do SQL Server Agent para a instância do SQL Server de arquivo QoE não está em execução no momento, a instalação pode continuar, mas após a instalação Verifique se o serviço do agente SQL está em execução e defina o tipo de inicialização como Automático para que o trabalho agendado seja executado. 
  
8. Na página configuração do cubo, forneça as seguintes informações:
    
   - **Arquivo de QoE nome do SQL Server:** Este é um campo somente leitura e foi corrigido para o nome de domínio totalmente qualificado do computador local. O cubo pode ser instalado somente da máquina que tem o banco de dados de arquivo QoE (observação. O próprio cubo pode ser instalado em um computador remoto. Veja abaixo)
    
   - **Instância de arquivo de QoE do SQL Server:** Nome da instância do SQL Server para onde o BD do arquivo de QoE está localizado. Para especificar uma instância padrão do SQL Server, deixe este campo em branco. Para especificar uma instância nomeada do SQL Server, insira o nome da instância (por exemplo, o nome\"após "). Se o componente de arquivo QoE tiver sido selecionado para a instalação, este campo será preenchido com o valor fornecido na página configuração de arquivo de QoE.
    
   - **Servidor de análise de cubo:** Nome da instância do serviço de análise do SQL Server para o qual o cubo será criado. Isso pode ser um computador diferente, mas o usuário de instalação precisa ser um membro dos administradores do servidor da instância do serviço de análise de SQL Server de destino.
    
     > [!NOTE]
     >  Para obter mais informações sobre como configurar permissões de administrador de servidor do Analysis Services, consulte [conceder permissões de administrador de servidor (Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx)
  
   - **Use várias partições:** O padrão é definido como "Multiple Partition", que exige Business Intelligence Edition ou Enterprise Edition do SQL Server. Para a edição Standard, selecione a opção "partição simples". Observe que o desempenho do processamento de cubo pode ser afetado se uma única partição for usada.
    
     > [!NOTE]
     >  A opção seleção para usar várias partições não pode ser alterada após a conclusão da instalação. Para alterá-lo, o recurso de cubo precisa ser desinstalado primeiro e reinstalado usando-se a opção "alterar" no painel de controle.
  
   - **Usuário do cubo – senha &amp; do nome do usuário:** Nome da conta de serviço de domínio e senha (mascarada) que dispararão o processamento de cubo. Se o componente de arquivo de QoE foi selecionado para a instalação, este campo será preenchido com o valor fornecido na página de configuração do arquivo para o usuário de trabalho do SQL Agent, mas recomendamos especificar uma conta de serviço de domínio diferente para que a configuração possa conceder o privilégio mínimo necessário.
    
9. Ao clicar em avançar, outra rodada de validação será realizada e qualquer problema será reportado. Após a conclusão bem-sucedida da validação, o instalador vai para a página de configuração do Portal. 
    
10. Na página configuração do portal, forneça as seguintes informações:
    
    - **Arquivo de QoE do SQL Server:** Nome da instância do SQL Server para a qual o banco de dados de arquivo QoE está localizado. Observe que, diferentemente da página de configuração de arquivo de QoE e da página de configuração de cubo, o nome do computador não é corrigido e deve ser fornecido. Se o componente de arquivo QoE tiver sido selecionado para a instalação, este campo será preenchido com o valor fornecido na página configuração de arquivo de QoE.
    
    - **Servidor de análise de cubo:** Nome da instância do serviço de análise do SQL Server para o qual o cubo está localizado. Se o componente de cubo foi selecionado para a instalação, este campo será preenchido previamente com o valor fornecido na página configuração do cubo.
    
    - **SQL Server do repositório:** Nome da instância do SQL Server na qual o banco de dados do repositório deve ser criado. Se o nome da instância do SQL Server para o qual o banco de dados de arquivo QoE estiver localizado tiver sido fornecido anteriormente na configuração (em outros componentes), esse campo será preenchido previamente com o nome da instância do SQL Server do banco de dados do recurso QoE. Pode ser qualquer instância do SQL Server.
    
    - **Banco de dados do repositório:** Por padrão, a opção é definida como "criar novo banco de dados". Como a atualização do BD do repositório não é suportada, a única circunstância sob a qual a opção "usar banco de dados existente" pode ser usada é se o banco de dados do repositório existente tiver o mesmo esquema que a compilação a ser instalada.
    
    - **Usuário do pool de aplicativos do IIS &amp; – senha do nome de usuário:** A conta em que o pool de aplicativos do IIS deve ser executado. Os campos nome de usuário e senha ficarão acinzentados se as contas internas do sistema estiverem marcadas. Esses campos só serão habilitados se "outros" estiver selecionado na caixa suspensa para que o usuário possa inserir as informações da conta do serviço de domínio.
    
11. Ao clicar em avançar, o último arredondamento da validação será feito para garantir que as instâncias do SQL Server sejam acessíveis usando as credenciais fornecidas e que o IIS está disponível na máquina. Após a conclusão bem-sucedida da validação, o instalador continuará com a configuração. 
    
Quando o instalador é concluído, provavelmente o trabalho do agente do SQL Server estará em andamento, fazendo a carga inicial dos dados de QoE e do processamento do cubo. Dependendo da quantidade de dados no QoE, o portal ainda não terá dados disponíveis para exibição. Para verificar o status de carregamento de dados e processamento de cubos, vá `http://<machinename>/CQD/#/Health`para. 
> [!NOTE]
> Observe que a URL para verificar o status do processamento do cubo de download diferencia maiúsculas de minúsculas. Se você inserir ' saúde ', a URL não funcionará. Você deve inserir ' saúde ' no final da URL com uma letra maiúscula H. 
  
Mensagens de log detalhadas serão mostradas se o modo de depuração estiver habilitado. Para habilitar o modo de depuração, vá para **%systemdrive%\Arquivos de Files\Skype para negócios 2015 CQD\QoEDataService\web.config**e atualize a seguinte linha para que o valor seja definido como **true**:

```
<add key="QoEDataLib.DebugMode" value="True" /> 
```

A página principal do portal pode ser `http://<machinename>/CQD`acessada pela. 
## <a name="managing-user-access-for-the-portal"></a>Gerenciando o acesso do usuário ao portal

Para gerenciar a autorização do usuário para o portal, recomendamos usar a autorização de URL, que foi introduzida no IIS 7,0. Para obter mais informações sobre a segurança do IIS, consulte Entendendo a [autorização da URL do iis 7,0 ](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).
  
Qualquer site da Web ou aplicativo Web herda a autorização de URL padrão configurada para todo o IIS, que normalmente é "permitir todos os usuários". Se o acesso ao portal precisar ser mais restritivo, os administradores poderão conceder acesso somente a um grupo específico de usuários editando as "regras de autorização".
  
![Implantar Qualidade da Chamada - Regras de Autorização no IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> O ícone regras de autorização não deve ser confundido com a "autorização .NET" na seção ASP.NET, que é um mecanismo de autorização diferente. 
  
Os administradores devem primeiro remover a regra herdada "permitir todos os usuários". Isso impede que qualquer usuário não autorizado acesse o Portal.
  
![Implantar o CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
Em seguida, os administradores devem adicionar novas regras de permissão e dar aos usuários específicos permissão para acessar o Portal. É recomendável que um grupo local chamado "CQDPortalUsers" seja criado para gerenciar os usuários.
  
![Implantar Painel de Qualidade da Chamada](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
Os detalhes de configuração são armazenados no Web. config localizado no diretório físico do Portal.
  
```
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

A próxima etapa é configurar o painel do CQD. Depois que os usuários forem autenticados pelo IIS, eles precisarão ter permissões de arquivo no diretório CQD para acessar o conteúdo do portal da Web. É possível alterar as ACLs por meio da guia Segurança das propriedades do diretório CQD para adicionar usuários ou grupos individuais; no entanto, a abordagem recomendada é deixar as permissões de arquivo intocadas. Em vez disso, altere a configuração do IIS para usar o processo de trabalho do IIS para acessar o diretório CQD independentemente do usuário que estiver autenticado. 
  
> [!IMPORTANT]
> É importante alterar essa configuração para o aplicativo CQD e não para os dois aplicativos de API: QoEDataService e QoERepositoryService. 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a>Configurando o acesso a arquivos para o CQD (painel)

1. Abra o editor de configuração para CQD.
    
     ![Implantar Painel de Qualidade da Chamada](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. Em seção, escolha **System. WebServer/serverRuntime**.
    
     ![Implantar Painel de Qualidade da Chamada](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. Altere authenticatedUserOverride para **UseWorkerProcessUser**.
    
     ![Painel implantar a qualidade da chamada, editor de configuração](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. Clique em **aplicar** no lado direito da página.
    
## <a name="known-issues"></a>Problemas conhecidos

### <a name="the-cqd-shows-no-data-after-deployment"></a>O CQD não mostra dados após a implantação

Você pode receber a seguinte mensagem de erro:

*Não foi possível executar a consulta enquanto a executamos no cubo. Use o editor de consultas para modificar a consulta e corrigir os problemas. Além disso, certifique-se de que o cubo esteja acessível.*

Isso significa que o cubo deve ser processado no SQL Server Analysis Services antes de ser usado no CQD. Você pode resolver isso seguindo estas etapas:

1. Abra o SQL Management Studio e selecione **Analysis Services**.

2. Expanda o objeto **QoECube** , selecione **métrica de QoE**, clique com o botão direito do mouse e, em seguida, escolha **procurar**. 

    Se isso retornar um navegador vazio, o cubo ainda não foi continuado.

3. Clique com o botão direito do mouse em **QoE Metric Metric** e escolha **process**.

4. Quando o processamento estiver concluído, clique com o botão direito do mouse novamente no objeto e escolha **procurar** para confirmar que a página do navegador agora mostra os dados. 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a>Os usuários têm problemas para fazer logon porque o instalador não cria as configurações corretas no IIS

Em casos raros, o instalador falha ao criar as configurações corretas no IIS. A alteração manual é necessária para permitir que os usuários façam logon no CQD. Se os usuários estiverem tendo problemas para conectar-se, siga estas etapas:
  
1. Abra o Gerenciador do IIS e navegue até site da Web padrão.
    
     ![Implantar Painel de Qualidade da Chamada](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. Clique em "autenticação". Se a "autenticação anônima", "representação ASP.NET", "autenticação de formulário" e "autenticação do Windows" não corresponderem às configurações mostradas abaixo, altere-as manualmente para corresponder às configurações abaixo. Todos os outros mecanismos de autenticação devem ser desabilitados.
    
     ![Implantar Painel de Qualidade da Chamada](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. Em "autenticação do Windows", clique em configurações avançadas no lado direito.
    
     ![Implantar Painel de Qualidade da Chamada](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. Defina "proteção estendida" para aceitar e marcar a caixa "habilitar autenticação de modo kernel".
    
     ![Implantar Painel de Qualidade da Chamada](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. Repita as etapas acima para cada uma das entradas "CQD", "QoEDataService" e "QoERepositoryService" abaixo "Default Web site".
    
Para associações de porta HTTP e HTTPS, o instalador criará associações de porta nos números de porta padrão (porta 80 para HTTP e porta 443 para HTTPS). Se houver outro site na máquina que usa essas associações, haverá um conflito e o comportamento do IIS não poderá ser previsto. A melhor maneira de evitar esse problema é certificar-se de que nenhum outro site esteja mapeado para as portas 80 e 443 antes de instalar o CQD. 
  
Para habilitar o SSL/TLS no IIS e forçar os usuários a se conectarem via HTTPS seguro em vez de HTTP:
  
1. Configurar o Secure Sockets Layer no IIS, consulte [configuração do Secure Sockets Layer no IIS 7](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx). Uma vez feito isso `http` , `https`substitua por.
    
2. Para obter instruções sobre como habilitar o TLS nas conexões do SQL Server, consulte [como habilitar a criptografia SSL para uma instância do SQL Server usando o console de gerenciamento Microsoft ](https://support.microsoft.com/en-us/kb/316898/).
    
## <a name="cube-sync-fails"></a>A sincronização do cubo falha

QoEMetrics pode conter alguns registros inválidos com base em relógios do usuário final. Se a distorção de tempo for maior que 60 yrs, a importação do cubo falhará.
  
 Verifique a hora de início e a hora de início/hora mínima usando as opções abaixo. Procure e exclua registros nas próximas distâncias e muito distantes, eles podem ser desconsiderados e irão quebrar os processos de sincronização.
  
- Selecione mínimo (StartTime) do CqdPartitionedStreamView
    
- Selecione MAX (StartTime) FROM CqdPartitionedStreamView
    
- Selecione mín (EndTime) em CqdPartitionedStreamView
    
- Selecione MAX (EndTime) do CqdPartitionedStreamView
    
## <a name="post-install-tasks"></a>Tarefas pós-instalação

### <a name="importing-buildings-and-networks"></a>Importando prédios e redes

Depois de instalar o CQD, realize as seguintes tarefas de configuração:
  
1. Definir tipos de construção (recomendado)
    
2. Definir tipos de propriedade de construção (recomendado)
    
3. Definir tipos de rede (altamente recomendado)
    
4. Importar prédios (recomendado)
    
5. Importar sub-redes (recomendado)
    
### <a name="define-building-types"></a>Definir tipos de construção

Os tipos de construção são usados para descrever as diferentes definições ou tipos de prédios dentro de sua organização. 
  
> [!NOTE]
> Esta etapa é opcional, mas recomendada. 
  
Exemplos
  
- Sede
    
- Escritório remoto
    
- Localização de joint venture
    
  **Exemplo de sintaxe SQL**
  
```
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

Os parâmetros BuildingTypeId e BuildingTypeDesc são obrigatórios.
  
### <a name="define-building-ownership-types"></a>Definir tipos de propriedade de construção

Os tipos de propriedade são usados para distinguir ativos de propriedade vs alugados.
  
> [!NOTE]
> Esta etapa é opcional, mas recomendada. 
  
Exemplos
  
- A contoso concedeu não-&amp;reativada
    
- A contoso concedeu&amp;re-F
    
- Pertencente à contoso
    
- Subsidiária alugada
    
  **Exemplo de sintaxe SQL**
  
```
INSERT INTO
[dbo].[CqdBuildingOwnershipType]
([OwnershipTypeId],
[OwnershipTypeDesc]
)

VALUES
(1,
'Contoso Owned'
)
```

Os parâmetros OwnershipTypeId e OwnershipTypeDesc são obrigatórios. 
  
### <a name="define-network-names"></a>Definir nomes de rede

Os tipos de rede são usados para descrever diferentes tipos de redes dentro da organização. Isso lhe dá a capacidade de filtrar (ou filtrar) tipos de rede específicos.
  
> [!NOTE]
> É altamente recomendável definir nomes de rede, mas é opcional. Se você decidir não definir nomes de rede, certifique-se de que cada entrada CqdNetwork tem um BuildId de 0. 
  
Exemplos
  
- VPN
    
- MULTIMÍDIA
    
  **Exemplo de sintaxe SQL**
  
```
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

Os parâmetros NetworkNameID e NetworkName são necessários, o parâmetro NetworkType é opcional, mas recomendado.
  
### <a name="import-buildings"></a>Prédios de importação

A importação de edifícios oferece a capacidade de criar ideias específicas (chamadas deficientes por prédio em WiFi/Wired etc.). 
  
> [!NOTE]
> Esta etapa é opcional, mas recomendada. 
  
Antes de importar um novo edifício, você já deve ter um BuildingKey predefinido identificado. Para fazer isso, emita o comando SQL "SELECT MAX (BuildingKey) FROM CqdBuilding" para identificar o valor atual e adicionar 1 ao resultado.
  
 **Exemplo de sintaxe SQL**
  
```
INSERT INTO [dbo].[CqdBuilding] 
( [BuildingKey]
,[BuildingName]
,[BuildingShortName]
,[OwnershipTypeId],
[BuildingTypeId]
)
VALUES
(2, 'Ann Arbor', 'AA', 0, 0)
```

Os parâmetros BuildingKey, buildName, BuildingShortName, OwnershipTypeId, BuildingTypeId são necessários, os outros parâmetros são opcionais.
  
### <a name="import-subnets"></a>Importar sub-redes

A importação de edifícios oferece a capacidade de criar ideias específicas (chamadas deficientes por prédio em WiFi/Wired etc.). 
  
> [!NOTE]
> Esta etapa é opcional, mas recomendada. 
  
Importar sub-redes e mapeá-las para os edifícios importados na última etapa. Se você optou por não preencher o NetworkName, certifique-se de que cada entrada desta tabela use um NetworkNameID de 0.
  
 **Exemplo de sintaxe SQL**
  
```
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',0,1,'2015-11-11')
```

A rede e os parâmetros UpdatedDate são necessários, os outros parâmetros são opcionais.
  
### <a name="optional-bssid"></a>Opcional: BSSID

Preencher as informações de BSSID proporciona mais correlação de fluxo WiFi por controlador ou rádio. Isso é uma adição à filtragem por meio da construção ou sub-rede. 
  
 **Exemplo de sintaxe SQL**
  
```
INSERT INTO [dbo].[CqdBssid]
([Ap],
[Bss],
[Building],
[ess],
[phy]
)
VALUES
('AP1','00-00-00-00-00-00','Aruba AP 1','Controller1','bgn')
```

**Detalhes do CqdBssidTable**

|**Como mostrado em CQD**|**Tabela CQDBssid**|**Exemplos de entradas**|
|:-----|:-----|:-----|
|AP NName  <br/> |WDS  <br/> |AP1  <br/> |
|BBssid  <br/> |BBS  <br/> |00-00-00-00-00-00 (você deve usar o fformat delimitado)  <br/> |
|Controle  <br/> |Edifício  <br/> |Ponto de acesso de Aruba 7  <br/> |
|Dispositivo  <br/> |ess  <br/> |Controller1  <br/> |
|Frequência  <br/> |phy  <br/> |bgn  <br/> |
   
### <a name="processing-the-imported-data"></a>Processando os dados importados

Por padrão, depois de importar dados de construção/rede, ele se aplicará somente aos registros gerados após esse ponto no tempo. 
  
Para marcar todos os registros anteriores com esses novos dados, você precisará executar o procedimento armazenado CqdUpdateBuilding, conforme mostrado abaixo: 
  
Dê a ela a data do seu primeiro registro (identifique que usando o comando SELECT MIN (StartTime) FROM CqdPartitionedStreamView SQL), um EndDate de amanhã, então NULL para os dois últimos valores.
  
Depois que os dados estiverem associados aos dados do fluxo, o cubo do SSIS precisará reprocessar todos os registros. Isso também se aplica durante a adição em massa de dados de BSSID/ISP. Verifique se a "processar completo" está selecionada.
  

