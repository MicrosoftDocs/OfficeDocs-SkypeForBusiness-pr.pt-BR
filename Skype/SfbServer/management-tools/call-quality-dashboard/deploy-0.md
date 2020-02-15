---
title: Implantar o painel de qualidade de chamada para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 'Resumo: Saiba mais sobre o processo de implantação do painel de qualidade de chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: d42d735ab5a60ec02ad2e1f4f696908996457c0b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042258"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a>Implantar o painel de qualidade de chamada para o Skype for Business Server
 
**Resumo:** Saiba mais sobre o processo de implantação do painel de qualidade de chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.
  
## <a name="deployment-overview"></a>Visão geral da implantação

O painel de qualidade de chamada (CQD) consiste em três componentes principais:
  
- **Arquivar banco**de dados, onde os dados de QoE (qualidade da experiência) são replicados e armazenados.
    
- **Cubo**, onde os dados do banco de dados de arquivo de QoE são agregados para acesso otimizado e rápido.
    
- **Portal**, onde os usuários podem facilmente consultar e Visualizar dados de QoE.
    
![Componentes do CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
O processo de instalação para o arquivo de QoE envolve a criação do banco de dados de arquivamento QoE, a implantação de um procedimento armazenado do SQL Server que moverá os dados do banco de dados de métricas de QoE de origem para o banco de dados de arquivo de distribuição e Configurando o trabalho do SQL Server Agent para executar o armazenamento procedimento em um intervalo regular. 
  
A implantação de cubo Obtém informações do usuário em que o arquivo de QoE está localizado, implanta o cubo e configura um trabalho regular do SQL Server Agent que atualizará o cubo em intervalos regulares.
  
A instalação do portal cria um banco de dados de repositório que armazena o mapeamento de usuários do CQD para relatórios/consultas de cada usuário. Em seguida, ele configura um aplicativo Web IIS, que é o painel em que os usuários podem ver um conjunto predefinido de relatórios, bem como personalizar e criar suas próprias consultas para visualizar dados do cubo. A instalação do portal cria dois aplicativos Web adicionais que expõem APIs para que os usuários acessem programaticamente o repositório e o cubo. (Essas APIs também são usadas internamente pelo painel).
  

|**Fase**|**Etapas**|**Funções e Associação de grupo**|**Documentação**|
|:-----|:-----|:-----|:-----|
|Instale os pré-requisitos de hardware e software.  <br/> |Decida sobre a configuração do CQD e escolha um SQL Server a partir do qual a instalação será executada.  <br/> |Usuário do domínio que é membro do grupo local de administradores.  <br/> |Seção "requisitos de pré-instalação" na documentação de implantação.  <br/> |
|Instale o CQD.  <br/> |Execute o MSI após o documento de implantação.  <br/> |Para executar a configuração, a conta de instalação deve ser um usuário de domínio que seja membro do grupo Administradores local e ter acesso de leitura ao banco de dados de métricas de QoE no servidor de monitoramento.  <br/> |Seções "etapas de contas e implantação" na documentação de implantação.  <br/> |
|Conceder acesso de usuário.  <br/> |Para gerenciar a autorização do usuário no portal, recomendamos o uso de autorização de URL, que foi introduzido no IIS 7,0. Para obter mais informações, consulte [Understanding IIS 7,0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).  <br/> |Usuário do domínio que é membro do grupo local de administradores.  <br/> |Gerenciar o acesso do usuário para a seção portal na documentação de implantação.  <br/> |
|Opcional: fornecer informações de mapeamento da sub-rede.  <br/> |Preencha as tabelas de mapeamento de rede e criação no banco de dados de arquivo de QoE.  <br/> |Uma conta com acesso de gravação ao banco de dados de arquivo de QoE.  <br/> |Seção "fornecendo informações de sub-rede" na documentação do usuário.  <br/> |
   


A implantação do painel de qualidade de chamada envolve a configuração da infraestrutura e a instalação do software. O procedimento a seguir descreve o processo.
  
## <a name="deployment-steps"></a>Etapas de implantação

1. Copie o CallQualityDashboard. msi para a máquina onde o componente de banco de dados de arquivamento do CQD deve ser instalado (esta é a máquina que tem o SQL Server instalado). 
    
2. Execute o MSI (o Windows solicitará a execução com o privilégio de administrador, faça isso). 
    
3. Aceite o EULA.
    
4. Selecione a pasta de destino onde os arquivos relacionados a componentes de painel de qualidade de chamada serão localizados ou aceite o local padrão.
    
5. Selecione todos os recursos.
    
6. Na página configuração de arquivo de QoE, forneça as seguintes informações:
    
   - **Métricas de QoE SQL Server:** Nome da instância do SQL Server para onde o banco de dados de métricas de QoE está localizado (será a fonte de dados).
    
   - **Arquivo de QoE nome do servidor SQL:** Este é um campo somente leitura e é corrigido para o nome de domínio totalmente qualificado do computador local. O banco de arquivo DB só pode ser instalado no computador local.
    
   - **Arquivo de QoE instância do SQL Server:** Um nome de instância local do SQL Server para onde o DB de arquivo morto deve ser criado. Para usar uma instância padrão do SQL Server, deixe este campo em branco. Para usar uma instância nomeada do SQL Server, especifique o nome da instância (por exemplo, o nome\"após ").
    
   - **Banco de dados de arquivo de QoE:** Por padrão, essa opção é definida como "criar novo banco de dados". Como a atualização do banco de dados de arquivo morto não é suportada, a única circunstância sob a qual a opção "usar banco de dados existente" pode ser usada é se o banco de dados de arquivo morto existente tiver o mesmo esquema que a compilação a ser instalada.
    
   - **Diretório de arquivos do banco de dados:** Caminho onde os arquivos de banco de dados (. MDF e. ldf) para o banco de dados de arquivo morto devem ser colocados. Ele deve estar em uma unidade (HDD2 na configuração de hardware recomendada) separada do sistema operacional. Observe que, como os nomes de arquivo são corrigidos na instalação, para evitar possíveis conflitos, é recomendável que um diretório em branco sem arquivos seja usado.
    
   - **Use várias partições:** O padrão é definido como "várias partições", que requer o Business Intelligence Edition ou Enterprise Edition do SQL Server. Para Standard Edition, selecione a opção "partição única". Observe que o desempenho do processamento do cubo pode ser afetado se uma única partição for usada.
    
     > [!NOTE]
     > A opção seleção para usar várias partições não pode ser alterada após a conclusão da instalação. Para alterá-la, o recurso de cubo precisa ser primeiro desinstalado e, em seguida, reinstalado usando a opção "alterar" no painel de controle. 
  
   - **Diretório de arquivos de partição:** Caminho onde as partições para o banco de dados de arquivo de QoE devem ser colocadas. Ele deve estar em uma unidade (HDD3 na configuração de hardware recomendada) separada da unidade do sistema operacional e da unidade de arquivos de log do banco de dados SQL. Observe que, como os nomes de arquivo são corrigidos na instalação, para evitar possíveis conflitos, é recomendável que um diretório em branco sem arquivos seja usado.
    
   - **Nome &amp; de usuário do trabalho do SQL Agent-senha:** Nome e senha da conta de serviço de domínio (mascarado) que serão usados para executar a etapa "dados de arquivo de QoE" do trabalho do SQL Server Agent (que executará o procedimento armazenado para buscar dados do banco de dados de métricas de QoE no banco de dados de arquivo morto, portanto, essa conta deverá ter acesso de leitura ao banco de dados de métricas de QoE, conforme Essa conta também precisa ter um logon na instância do SQL Server de arquivo de QoE).
    
     > [!NOTE]
     > A conta sob a qual a instância do SQL Server está sendo executada, como NT SERVICE\MSSQLSERVER, deve ter acesso/permissão aos diretórios acima para que a instalação seja bem-sucedida. Para obter detalhes, consulte [Configure File System Permissions for Database Engine Access](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx)
  
7. Ao clicar em avançar, o instalador executará verificações de pré-requisitos e relatará se algum problema for encontrado. Quando as verificações de pré-requisitos passam, o instalador vai para a página de configuração do cubo. 
    
    > [!NOTE]
    > Se o instalador mostrar uma mensagem de aviso informando que o serviço do SQL Server Agent para o arquivo de QoE instância do SQL Server não está em execução, a instalação pode continuar, mas após a instalação, verifique se o serviço do SQL Agent está em execução e defina o tipo de inicialização como Automático para que o trabalho agendado seja executado. 
  
8. Na página configuração de cubo, forneça as seguintes informações:
    
   - **Arquivo de QoE nome do servidor SQL:** Este é um campo somente leitura e é corrigido para o nome de domínio totalmente qualificado do computador local. O cubo pode ser instalado apenas da máquina que tem um banco de dados de arquivo de QoE (observação. O próprio cubo pode ser instalado em uma máquina remota. Veja abaixo)
    
   - **Arquivo de QoE instância do SQL Server:** Nome da instância do SQL Server para onde o DB de arquivo de QoE está localizado. Para especificar uma instância padrão do SQL Server, deixe este campo em branco. Para especificar uma instância nomeada do SQL Server, digite o nome da instância (por exemplo, o nome\"após "). Se o componente de arquivo de QoE foi selecionado para a instalação, este campo será preenchido previamente com o valor fornecido na página configuração de arquivo de QoE.
    
   - **Servidor de análise de cubo:** Nome da instância do serviço de análise do SQL Server para onde o cubo deve ser criado. Pode ser uma máquina diferente, mas o usuário de instalação precisa ser membro dos administradores de servidor da instância do serviço de análise de destino do SQL Server.
    
     > [!NOTE]
     >  Para obter mais informações sobre como configurar permissões de administrador de servidor do Analysis Services, consulte [Grant Server Administrative Permissions (Analysis Services)](https://msdn.microsoft.com/library/ms174561.aspx)
  
   - **Use várias partições:** O padrão é definido como "várias partições", que requer o Business Intelligence Edition ou Enterprise Edition do SQL Server. Para Standard Edition, selecione a opção "partição única". Observe que o desempenho do processamento do cubo pode ser afetado se uma única partição for usada.
    
     > [!NOTE]
     >  A opção seleção para usar várias partições não pode ser alterada após a conclusão da instalação. Para alterá-la, o recurso de cubo precisa ser primeiro desinstalado e, em seguida, reinstalado usando a opção "alterar" no painel de controle.
  
   - **Usuário de cubo-senha &amp; de nome de usuário:** Nome e senha da conta de serviço de domínio (mascarado) que dispararão o processamento de cubo. Se o componente de arquivo de QoE foi selecionado para a instalação, este campo será preenchido previamente com o valor fornecido na página configuração de arquivo morto para o usuário de trabalho do SQL Agent, mas recomendamos especificar uma conta de serviço de domínio diferente para que a instalação possa conceder a privilégio menos necessário para ele.
    
9. Ao clicar em avançar, uma nova rodada de validação será executada e qualquer problema será relatado. Após a conclusão bem-sucedida da validação, o instalador vai para a página de configuração do Portal. 
    
10. Na página configuração do portal, forneça as seguintes informações:
    
    - **Arquivo de QoE do SQL Server:** Nome da instância do SQL Server para onde o banco de dados de arquivo de QoE está localizado. Observe que, diferentemente da página de configuração de arquivo de QoE e da página de configuração de cubo, o nome do computador não é corrigido e deve ser fornecido. Se o componente de arquivo de QoE foi selecionado para a instalação, este campo será preenchido previamente com o valor fornecido na página configuração de arquivo de QoE.
    
    - **Servidor de análise de cubo:** Nome da instância do serviço de análise do SQL Server para onde o cubo está localizado. Se o componente de cubo foi selecionado para a instalação, este campo será preenchido previamente com o valor fornecido na página configuração de cubo.
    
    - **SQL Server do repositório:** Nome da instância do SQL Server onde o banco de dados do repositório deve ser criado. Se o nome da instância do SQL Server para onde o banco de dados de arquivo de QoE está localizado tiver sido fornecido anteriormente na configuração (em outros componentes), esse campo será preenchido previamente com o nome da instância do SQL Server do banco de dados do servidor da QoE. Pode ser qualquer instância do SQL Server.
    
    - **Banco de dados de repositório:** Por padrão, a opção é definida como "criar novo banco de dados". Como a atualização do banco de dados de repositório não é suportada, a única circunstância sob a qual a opção "usar banco de dados existente" pode ser usada se o banco de dados do repositório existente tiver o mesmo esquema que a compilação a ser instalada.
    
    - **Usuário do pool de aplicativos do IIS &amp; senha do nome de usuário:** A conta na qual o pool de aplicativos do IIS deve ser executado. Os campos nome de usuário e senha serão esmaecidos se as contas de sistema internas estiverem selecionadas. Esses campos só serão habilitados se "outros" estiver selecionado na caixa suspensa para que o usuário possa inserir as informações da conta de serviço de domínio.
    
11. Ao clicar em avançar, a última rodada de validação será feita para garantir que as instâncias do SQL Server sejam acessíveis usando as credenciais fornecidas e que o IIS esteja disponível no computador. Após a conclusão bem-sucedida da validação, o instalador prosseguirá com a configuração. 
    
Quando o instalador estiver concluído, provavelmente o trabalho do SQL Server Agent estará em andamento, realizando a carga inicial dos dados de QoE e o processamento de cubos. Dependendo da quantidade de dados no QoE, o portal ainda não terá dados disponíveis para exibição. Para verificar o status da carga de dados e processamento de cubo, acesse `http://<machinename>/CQD/#/Health`. 
> [!NOTE]
> Observe que a URL para verificar o status do processamento do cubo de download diferencia maiúsculas de minúsculas. Se você digitar "saúde", a URL não funcionará. Você deve inserir "Health" no final da URL com um H maiúsculo. 
  
As mensagens de log detalhadas serão mostradas se o modo de depuração estiver habilitado. Para habilitar o modo de depuração, vá para **%systemdrive%\Arquivos de Files\Skype para negócios 2015 CQD\QoEDataService\web.config**e atualize a linha a seguir para que o valor seja definido como **true**:

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

A página do portal principal é acessível `http://<machinename>/CQD`via. 
## <a name="managing-user-access-for-the-portal"></a>Gerenciando o acesso do usuário ao portal

Para gerenciar a autorização do usuário no portal, recomendamos o uso de autorização de URL, que foi introduzido no IIS 7,0. Para obter mais informações sobre a segurança do IIS, consulte [Understanding iis 7,0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).
  
Qualquer site ou aplicativo da Web herdará a autorização de URL padrão configurada para todo o IIS, que normalmente é "permitir todos os usuários". Se o acesso ao portal precisar ser mais restritivo, os administradores podem conceder acesso apenas ao grupo específico de usuários editando as "regras de autorização".
  
![Implantar regras de autorização de qualidade de chamada no IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> O ícone de regras de autorização não deve ser confundido com a "autorização .NET" na seção ASP.NET, que é um mecanismo de autorização diferente. 
  
Os administradores devem primeiro remover a regra herdada "permitir todos os usuários". Isso impede que usuários não autorizados acessem o Portal.
  
![Implantar CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
Em seguida, os administradores devem adicionar novas regras de permissão e conceder aos usuários específicos a permissão para acessar o Portal. É recomendável que um grupo local chamado "CQDPortalUsers" seja criado para gerenciar os usuários.
  
![Implantar painel de qualidade de chamada](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
Os detalhes de configuração são armazenados no Web. config localizado no diretório físico do Portal.
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

A próxima etapa é configurar o painel do CQD. Depois que os usuários são autenticados pelo IIS, eles precisarão ter permissões de arquivo no diretório CQD para acessar o conteúdo do portal da Web. É possível alterar as ACLs por meio da guia Segurança das propriedades do diretório CQD para adicionar usuários individuais ou grupos; no entanto, a abordagem recomendada é deixar as permissões de arquivo inalteradas. Em vez disso, altere a configuração do IIS para usar o processo de trabalho do IIS para acessar o diretório CQD, independentemente de qual usuário é autenticado. 
  
> [!IMPORTANT]
> É importante apenas alterar essa configuração para o aplicativo CQD e não para os dois aplicativos de API: QoEDataService e QoERepositoryService. 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a>Configurando o acesso a arquivos para o CQD (painel)

1. Abra o editor de configuração do CQD.
    
     ![Implantar painel de qualidade de chamada](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. Em seção, escolha **System. WebServer/serverRuntime**.
    
     ![Implantar painel de qualidade de chamada](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. Altere authenticatedUserOverride para **UseWorkerProcessUser**.
    
     ![Implantar painel de qualidade da chamada-editor de configuração](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. Clique em **aplicar** no lado direito da página.
    
## <a name="known-issues"></a>Problemas Conhecidos

### <a name="the-cqd-shows-no-data-after-deployment"></a>O CQD não mostra dados após a implantação

Você pode receber o seguinte erro:

*Não foi possível executar a consulta ao executá-la no cubo. Use o editor de consultas para modificar a consulta e corrigir problemas. Além disso, certifique-se de que o cubo está acessível.*

Isso significa que o cubo deve ser processado no SQL Server Analysis Services antes de ser usado no CQD. É possível resolver isso, seguindo estas etapas:

1. Abra o SQL Management Studio e selecione o **Analysis Services**.

2. Expanda o objeto **QoECube** , selecione **métrica de QoE**, clique com o botão direito do mouse e escolha **procurar**. 

    Se isso retornar um navegador vazio, o cubo ainda não foi continuado.

3. Clique com o botão direito do mouse em **QoE métrico** e escolha **processo**.

4. Quando o processamento estiver concluído, clique com o botão direito do mouse novamente no objeto e escolha **procurar** para confirmar que a página do navegador agora mostra os dados. 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a>Os usuários têm problemas para fazer logon porque o instalador não cria as configurações corretas no IIS

Em casos raros, o instalador não cria as configurações corretas no IIS. A alteração manual é necessária para permitir que os usuários façam logon no CQD. Se os usuários estiverem tendo problemas para fazer logon, siga estas etapas:
  
1. Abra o Gerenciador do IIS e navegue até o site da Web padrão.
    
     ![Implantar painel de qualidade de chamada](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. Clique em "autenticação". Se a "autenticação anônima", "representação de ASP.NET", "autenticação de formulário" e "autenticação do Windows" não corresponder às configurações mostradas abaixo, altere-as manualmente para que correspondam às configurações abaixo. Todos os outros mecanismos de autenticação devem ser desabilitados.
    
     ![Implantar painel de qualidade de chamada](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. Em "autenticação do Windows", clique em configurações avançadas no lado direito.
    
     ![Implantar painel de qualidade de chamada](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. Defina "proteção estendida" para aceitar e marcar a caixa "habilitar autenticação de modo kernel".
    
     ![Implantar painel de qualidade de chamada](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. Repita as etapas acima para cada uma das entradas "CQD", "QoEDataService" e "QoERepositoryService", abaixo de "Default Web site".
    
Para associações de porta HTTP e HTTPS, o instalador criará associações de porta nos números de porta padrão (porta 80 para HTTP e porta 443 para HTTPS). Se houver outro site na máquina que usa essas associações, haverá um conflito e o comportamento do IIS não poderá ser previsto. A melhor maneira de evitar esse problema é certificar-se de que nenhum outro site esteja mapeado para as portas 80 e 443 antes da instalação do CQD. 
  
Para habilitar o SSL/TLS no IIS e forçar os usuários a se conectar via HTTPS seguro em vez de HTTP:
  
1. Configure Secure Sockets Layer no IIS, consulte [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx). Após concluir, substitua `http` por `https`.
    
2. Para instruções sobre como habilitar o TLS nas conexões do SQL Server, confira [como habilitar a criptografia SSL para uma instância do SQL Server usando o console de gerenciamento Microsoft](https://support.microsoft.com/kb/316898/).
    
## <a name="cube-sync-fails"></a>Falha na sincronização do cubo

O QoEMetrics pode conter alguns registros inválidos com base nos relógios dos usuários finais. Se a diferença de tempo for maior que 60 yrs, a importação de cubo falhará.
  
 Verifique o min e o Max StartTime/EndTime usando as seleções abaixo. Procure e exclua os registros distantes e distantes no futuro, eles podem ser desconsiderados e quebrar os processos de sincronização.
  
- Selecione mín (início) de CqdPartitionedStreamView
    
- Selecione MAX (StartTime) de CqdPartitionedStreamView
    
- Selecione mín (EndTime) de CqdPartitionedStreamView
    
- Selecione máximo (EndTime) de CqdPartitionedStreamView
    
## <a name="post-install-tasks"></a>Tarefas pós-instalação

### <a name="importing-buildings-and-networks"></a>Importando edifícios e redes

Após instalar o CQD, execute as seguintes tarefas de configuração:
  
1. Definir tipos de construção (recomendado)
    
2. Definir tipos de propriedade de criação (recomendado)
    
3. Definir tipos de rede (altamente recomendado)
    
4. Edifícios de importação (recomendado)
    
5. Importar sub-redes (recomendado)
    
### <a name="define-building-types"></a>Definir tipos de construção

Os tipos de construção são usados para descrever as diferentes definições de prédios ou tipos dentro da sua organização. 
  
> [!NOTE]
> Esta etapa é opcional, mas recomendada. 
  
Exemplos
  
- Sede
    
- Escritórios remotos
    
- Localização de joint venture
    
  **Exemplo de sintaxe SQL**
  
```SQL
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

Os parâmetros BuildingTypeId e BuildingTypeDesc são obrigatórios.
  
### <a name="define-building-ownership-types"></a>Definir tipos de propriedade de criação

Os tipos de propriedade são usados para distinguir ativos de propriedade vs alugados.
  
> [!NOTE]
> Esta etapa é opcional, mas recomendada. 
  
Exemplos
  
- Não-Redirecionado&amp;F concedido da contoso
    
- Da Contoso concedido RE&amp;F
    
- Propriedade da contoso
    
- Subsidiária alugada
    
  **Exemplo de sintaxe SQL**
  
```SQL
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

Os tipos de rede são usados para descrever diferentes tipos de redes dentro da organização. Isso dá a você a capacidade de filtrar (ou filtrar) tipos de rede específicos.
  
> [!NOTE]
> É altamente recomendável definir nomes de rede, mas é opcional. Se você decidir não definir nomes de rede, certifique-se de que cada entrada CqdNetwork tenha um Buildingid de 0. 
  
Exemplos
  
- VPN
    
- Labs
    
  **Exemplo de sintaxe SQL**
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

Os parâmetros NetworkNameID e NetworkName são necessários, o parâmetro NetworkType é opcional, mas recomendado.
  
### <a name="import-buildings"></a>Edifícios de importação

A importação de edifícios oferece a capacidade de criar insights específicos (chamadas ruins por prédio em WiFi/Wired, etc.). 
  
> [!NOTE]
> Esta etapa é opcional, mas recomendada. 
  
Antes de importar um novo edifício, você já deve ter um BuildingKey predefinido identificado. Para fazer isso, emita o comando "SELECT MAX (BuildingKey) FROM CqdBuilding" para identificar o valor atual e adicionar 1 ao resultado.
  
 **Exemplo de sintaxe SQL**
  
```SQL
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

Os parâmetros BuildingKey, Buildingname, BuildingShortName, OwnershipTypeId, BuildingTypeId são obrigatórios, os outros parâmetros são opcionais.
  
### <a name="import-subnets"></a>Importar sub-redes

A importação de edifícios oferece a capacidade de criar insights específicos (chamadas ruins por prédio em WiFi/Wired, etc.). 
  
> [!NOTE]
> Esta etapa é opcional, mas recomendada. 
  
Importe sub-redes e mapeie-as para os edifícios importados na última etapa. Se você optou por não preencher o NetworkName, certifique-se de que cada entrada desta tabela use um NetworkNameID de 0.
  
 **Exemplo de sintaxe SQL**
  
```SQL
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

O preenchimento de informações de BSSID fornece correlação de fluxo de WiFi adicional por controlador ou rádio. Isso é uma adição à filtragem por compilação ou sub-rede. 
  
 **Exemplo de sintaxe SQL**
  
```SQL
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

|**Conforme mostrado no CQD**|**Tabela CQDBssid**|**Exemplos de entradas**|
|:-----|:-----|:-----|
|AP NName  <br/> |APS  <br/> |AP1  <br/> |
|BBssid  <br/> |BBS  <br/> |00-00-00-00-00-00 (você deve usar o fformat delimitado)  <br/> |
|Controlador  <br/> |Build  <br/> |Ponto de acesso 7 de Aruba  <br/> |
|Device  <br/> |ESS  <br/> |Controller1  <br/> |
|Radio  <br/> |PHY  <br/> |bgn  <br/> |
   
### <a name="processing-the-imported-data"></a>Processamento dos dados importados

Por padrão, depois que você importa dados de construção/rede, ele só se aplica aos registros gerados após esse momento determinado. 
  
Para marcar todos os registros anteriores com esses novos dados, você precisará executar o procedimento armazenado CqdUpdateBuilding, conforme mostrado abaixo: 
  
Dê a ela a data do primeiro registro (identifique que usando o comando SELECT MIN (StartTime) do CqdPartitionedStreamView SQL), um EndDate de amanhã, então nulo para os dois últimos valores.
  
Depois que os dados são associados aos dados de fluxo, o cubo do SSIS precisa reprocessar todos os registros. Isso também se aplica ao acréscimo de dados de BSSID/ISP em massa. Assegure-se de que "processo completo" esteja selecionado.
  

