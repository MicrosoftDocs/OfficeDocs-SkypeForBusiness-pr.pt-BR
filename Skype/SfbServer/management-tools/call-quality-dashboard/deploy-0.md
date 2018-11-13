---
title: Implantar o painel de controle de qualidade de chamada para Skype para Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 'Resumo: Saiba mais sobre o processo de implantação para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.'
ms.openlocfilehash: 31e1dc8d5508c7d3d31de0ec3af0b9c8c06a6c40
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294986"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server-2015"></a>Implantar o painel de controle de qualidade de chamada para Skype para Business Server 2015
 
**Resumo:** Saiba mais sobre o processo de implantação para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.
  
## <a name="deployment-overview"></a>Visão geral da implantação

Painel de controle de qualidade de chamada (CQD) consiste em três componentes principais:
  
- **Banco de dados de arquivamento**, onde os dados de qualidade da experiência (QoE) são replicados e armazenados.
    
- **Cubo**, onde os dados do banco de dados de arquivo morto de QoE são agregados para otimizados e acesso rápido.
    
- **Portal**, onde os usuários podem facilmente consultar e visualizar os dados do QoE.
    
![Componentes do CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
O processo de instalação para arquivo morto de QoE envolve criando o banco de dados de arquivo morto de QoE, implantando um procedimento armazenado do SQL Server que irá mover os dados da fonte de banco de dados de métricas de QoE em banco de dados de arquivamento do QoE e configurando o trabalho do SQL Server Agent para executar o armazenado procedimento em intervalos regulares. 
  
Implantação de cubo obtém informações do usuário no qual o arquivamento de QoE está localizado, implanta o cubo e configura um trabalho de agente regular do SQL Server que irá atualizar o cubo em intervalos regulares.
  
Instalação do portal cria um banco de dados do repositório que armazena o mapeamento de usuários CQD/consultas de relatórios de cada usuário. Em seguida, ele configura um aplicativo web do IIS que é o painel onde os usuários podem ver um conjunto predefinido de relatórios, bem como personalizar e criar suas próprias consultas para visualizar os dados do cubo. A instalação do portal cria dois aplicativos web adicionais que expõe APIs para os usuários acessarem programaticamente o repositório e o cubo. (Essas APIs são usados internamente pelo painel também.)
  

|**Fase**|**Etapas**|**Funções e associação de grupo**|**Documentação**|
|:-----|:-----|:-----|:-----|
|Instale pré-requisitos de hardware e software.  <br/> |Decidir sobre a configuração de CQD e escolha um SQL Server a partir do qual efetuar a instalar.  <br/> |Usuário do domínio que é membro do grupo local de administradores.  <br/> |Seção "Pré-requisitos de instalar" na documentação de implantação.  <br/> |
|Instale o CQD.  <br/> |Execute o MSI seguindo o documento de implantação.  <br/> |Para executar a instalação, a conta de instalação deve ser um usuário de domínio que seja membro do grupo Administradores local e ter acesso de leitura ao banco de dados de métricas de QoE no Monitoring Server.  <br/> |Seções "Contas e as etapas de implantação" na documentação de implantação.  <br/> |
|Conceder acesso de usuário.  <br/> |Para gerenciar a autorização de usuários ao Portal, recomendamos o uso de autorização de URL, que foi introduzido no IIS 7.0. Para obter mais informações, consulte [Understanding IIS 7.0 a autorização de URL](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).  <br/> |Usuário do domínio que é membro do grupo local de administradores.  <br/> |Gerenciando o acesso de usuário para a seção de Portal na documentação de implantação.  <br/> |
|Opcional: Forneça informações de mapeamento de sub-rede.  <br/> |Preencha a rede e tabelas de mapeamento de construção no banco de dados de arquivo morto de QoE.  <br/> |Uma conta com acesso de gravação no banco de dados de arquivo morto de QoE.  <br/> |Seção "Fornecendo informações de sub-rede" na documentação do usuário.  <br/> |
   


Configurando a infraestrutura e instalando o software envolve a implantação do painel de controle de qualidade de chamada. O procedimento a seguir destaca o processo.
  
## <a name="deployment-steps"></a>Etapas da implantação

1. Copie o CallQualityDashboard.msi máquina onde deve ser instalado o componente de banco de dados de arquivamento do CQD (essa é a máquina que tenha o SQL Server instalado). 
    
2. Executar o MSI (Windows perguntará executado com privilégios de administrador, fazê-lo). 
    
3. Aceite o EULA.
    
4. Selecione a pasta de destino onde os arquivos relacionados aos componentes do painel de controle de qualidade de chamada vai ser localizado ou aceite o local padrão.
    
5. Selecione todos os recursos.
    
6. Na página de configuração de arquivamento de QoE, forneça as seguintes informações:
    
   - **Métricas de QoE SQL Server:** Nome de instância do SQL Server para onde se encontra o banco de dados de métricas de QoE (Isso será a fonte de dados).
    
   - **Nome de arquivo morto de QoE do SQL Server:** Este é o campo somente leitura e fixa com o nome de domínio totalmente qualificado da máquina local. BD de arquivamento pode ser instalado somente na máquina local.
    
   - **Arquivamento de QoE instância do SQL Server:** Um nome de instância de SQL Server local para onde o banco de dados de arquivo morto deve ser criada. Para usar uma instância do SQL Server padrão, deixe este campo em branco. Para usar uma instância nomeada do SQL Server, especifique o nome da instância (por exemplo, o nome após o "\").
    
   - **Banco de dados de arquivamento do QoE:** Por padrão, essa opção é definida como "Criar novo banco de dados". Desde que não há suporte para a atualização do banco de dados de arquivamento, a única circunstância sob a qual a opção "Usar o banco de dados existente" pode ser usada é se o banco de dados existente do arquivo morto tem o mesmo esquema que a compilação seja instalado.
    
   - **Diretório de arquivos de banco de dados:** Caminho onde os arquivos de banco de dados (arquivos. mdf e. ldf) para o banco de dados de arquivo morto devem ser colocados. Este deve ser em uma unidade separada (HDD2 na configuração de hardware recomendada) do sistema operacional. Observe que como os nomes de arquivo são corrigidos na instalar, para evitar conflitos potenciais, é recomendável que um diretório em branco com nenhum arquivo ser usado.
    
   - **Use várias partições:** O padrão é definido como "Vários partição", que requer a edição de Business Intelligence ou Enterprise edition do SQL Server. Para o Standard edition, selecione a opção de "Única partição". Observe que o desempenho de processamento de cubo pode ser afetado se única partição for usada.
    
     > [!NOTE]
     > A seleção da opção usar várias partições não pode ser alterada depois que terminar a instalação. Para alterá-lo, o cubo de recurso deve ser o primeiro desinstalada e então reinstalado usando a opção "Alterar" no painel de controle. 
  
   - **Partição de diretório do arquivo:** Caminho para onde as partições do banco de dados de arquivo morto de QoE devem ser colocadas. Este deve ser em uma unidade separada (HDD3 na configuração de hardware recomendada) da unidade do sistema operacional e unidade de arquivos de log de banco de dados SQL. Observe que como os nomes de arquivo são corrigidos na instalar, para evitar conflitos potenciais, é recomendável que um diretório em branco com nenhum arquivo ser usado.
    
   - **Usuário de trabalho do SQL Agent - nome de usuário &amp; senha:** Nome de conta de serviço de domínio e a senha (mascaradas) que será usada para executar a etapa de "Dados de arquivamento do QoE" do trabalho de SQL Server Agent (que executará o procedimento armazenado para buscar dados do banco de dados de métricas de QoE em Archive DB, portanto, essa conta deve ter acesso de leitura ao banco de dados de métricas de QoE,  conforme indicado na seção contas. Essa conta também precisa ter um logon na instância do QoE Archive SQL Server).
    
     > [!NOTE]
     > A conta que a instância do SQL Server está sendo executado em, como NT SERVICE\MSSQLSERVER, deve ter permissão de acesso/para os diretórios de dado acima para a instalação ter sucesso. Para obter detalhes, consulte [Configurar permissões do sistema do arquivo para acesso do mecanismo de banco de dados](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)
  
7. Após clicar em Avançar, o instalador executará verificações de pré-requisito e o relatório se ocorrerem problemas. Quando verificações de pré-requisito tudo secreta, o instalador irão para a página Configuração do cubo. 
    
    > [!NOTE]
    > Se o instalador mostrar uma mensagem de aviso que o serviço SQL Server Agent para a instância do SQL Server QoE arquivo morto não está executando no momento, pode continuar a instalação, mas pós-instalação Certifique-se de que o serviço do agente do SQL está em execução e defina o tipo de inicialização como Automático, para que o trabalho agendado seja executado. 
  
8. Na página Configuração do cubo, forneça as seguintes informações:
    
   - **Nome de arquivo morto de QoE do SQL Server:** Este é o campo somente leitura e fixa com o nome de domínio totalmente qualificado da máquina local. Cubo pode ser instalado somente da máquina que tenha um banco de dados de arquivamento de QoE (nota. Próprio cubo pode ser instalado em um computador remoto. Veja abaixo)
    
   - **Arquivamento de QoE instância do SQL Server:** Nome de instância do SQL Server para onde se encontra o banco de dados de arquivo morto de QoE. Para especificar uma instância do SQL Server padrão, deixe este campo em branco. Para especificar uma instância nomeada do SQL Server, insira o nome da instância (por exemplo, o nome após o "\"). Se o componente de arquivo morto de QoE foi selecionado para a instalação, esse campo será pré-preenchido com o valor fornecido na página Configuração de arquivamento de QoE.
    
   - **Cubos do Analysis Server:** Nome de instância do SQL Server Analysis Service para onde o cubo deve ser criada. Isso pode ser uma máquina diferente, mas o usuário de instalação deve ser um membro do grupo Administradores de servidor da instância do SQL Server Analysis Service de destino.
    
     > [!NOTE]
     >  Para obter mais informações sobre como configurar permissões de administrador do servidor de serviços de análise, consulte [Conceder permissões de administrador do servidor (Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx)
  
   - **Use várias partições:** O padrão é definido como "Vários partição", que requer a edição de Business Intelligence ou Enterprise edition do SQL Server. Para o Standard edition, selecione a opção de "Única partição". Observe que o desempenho de processamento de cubo pode ser afetado se única partição for usada.
    
     > [!NOTE]
     >  A seleção da opção usar várias partições não pode ser alterada depois que terminar a instalação. Para alterá-lo, o cubo de recurso deve ser o primeiro desinstalada e então reinstalado usando a opção "Alterar" no painel de controle.
  
   - **User - nome de usuário de cubos &amp; senha:** Nome de conta de serviço de domínio e a senha (mascaradas) que acionará o processamento do cubo. Se o componente de arquivo morto de QoE foi selecionado para a instalação, esse campo será preenchido com o valor fornecido na página Configuração de arquivamento para o usuário de trabalho de agente do SQL, mas recomendamos que você especificar uma conta de serviço de domínio diferente para que a instalação pode conceder a privilégios mínimos necessários a ela.
    
9. Quando você clica em seguida, outra round de validação será realizada e qualquer problema seja relatado. Após a conclusão bem-sucedida da validação, o instalador irão para a página de configuração de Portal. 
    
10. Na página Configuração do Portal, forneça as seguintes informações:
    
    - **Arquivamento de QoE SQL Server:** Nome de instância do SQL Server para onde se encontra o banco de dados de arquivo morto de QoE. Observe que, ao contrário da página de configuração de arquivamento do QoE e a página Configuração do cubo, o nome da máquina não for corrigido e deve ser fornecido. Se o componente de arquivo morto de QoE foi selecionado para a instalação, esse campo será pré-preenchido com o valor fornecido na página Configuração de arquivamento de QoE.
    
    - **Cubos do Analysis Server:** Nome de instância do SQL Server Analysis Service para onde se encontra o cubo. Se o componente de cubo foi selecionado para a instalação, esse campo será pré-preenchido com o valor fornecido na página Configuração do cubo.
    
    - **Repositório SQL Server:** Nome da instância do SQL Server onde o banco de dados do repositório deve ser criada. Se o nome da instância do SQL Server para onde se encontra o banco de dados de arquivo morto de QoE foram fornecido anteriormente na configuração (em outros componentes), esse campo será pré-preenchido com o nome da instância de QoE Archive DB SQL Server. Isso pode ser qualquer instância do SQL Server.
    
    - **Banco de dados de repositório:** Por padrão, a opção é definida como "Criar novo banco de dados". Desde que não há suporte para a atualização do banco de dados do repositório, a única circunstância sob a qual a opção "Usar o banco de dados existente" pode ser usada é se o banco de dados do repositório existente tem o mesmo esquema que a compilação seja instalado.
    
    - **Usuário do Pool de aplicativos do IIS - nome de usuário &amp; senha:** A conta que deve ser executadas sob o pool de aplicativos do IIS. Os campos nome de usuário e senha estará esmaecidos se as contas de sistema interno forem selecionadas. Esses campos só serão ativados se "Other" está selecionada na caixa suspensa para que o usuário pode digitar as informações de conta de serviço de domínio.
    
11. Quando você clica em seguida, será feito o round final de validação para garantir que as instâncias do SQL Server são acessíveis usando as credenciais fornecidas e que o IIS está disponível na máquina. Após a conclusão bem-sucedida da validação, o instalador prosseguirá com a instalação. 
    
O instalador é feito, provavelmente o trabalho do SQL Server Agent ficará em andamento, fazendo o carregamento inicial dos dados QoE e o processamento do cubo. Dependendo da quantidade de dados de QoE, o portal não terá dados disponíveis para exibição ainda. Para verificar o status da carga de dados e processamento de cubo, vá para `http://<machinename>/CQD/#/Health`. 
> [!NOTE]
> Observe que a URL para a verificação do status do processamento de cubo download diferencia maiusculas de minúsculas. Se você digitar 'integridade' a URL não funcionará. Você deve inserir integridade no final da URL com uma letra maiuscula H. 
  
Mensagens de log detalhado serão exibidas se o modo de depuração está habilitado. Para habilitar o modo de depuração, vá para **%SYSTEMDRIVE%\Program Files\Skype para negócios 2015 CQD\QoEDataService\web.config**e atualizar a seguinte linha para que o valor é definido como **True**:

```
<add key="QoEDataLib.DebugMode" value="True" /> 
```

A página de portal principal é acessível via `http://<machinename>/CQD`. 
## <a name="managing-user-access-for-the-portal"></a>Gerenciando o acesso de usuário para o Portal

Para gerenciar a autorização de usuários ao Portal, recomendamos o uso de autorização de URL, que foi introduzido no IIS 7.0. Para obter mais informações sobre a segurança do IIS, consulte [Noções básicas sobre o IIS 7.0 a autorização de URL ](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).
  
Qualquer aplicativo web de site ou web herdam o padrão de autorização de URL configurados para o IIS inteira, que geralmente são "Permitir que todos os usuários". Se precisar de acesso ao Portal ser mais restritivo, então os administradores podem conceder acesso aos apenas o grupo específico de usuários por meio da edição "Regras de autorização".
  
![Implantar Qualidade da Chamada - Regras de Autorização no IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> O ícone de regras de autorização não é deve ser confundido com a "autorização .NET" sob a seção ASP.NET, que é um mecanismo de autorização diferentes. 
  
Os administradores devem primeiro remover a regra herdadas "permitir que todos os usuários". Isso impede que os usuários não autorizados acessar o Portal.
  
![Implantar CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
Em seguida, os administradores devem adicionar novas regras permitir e conceder a permissão para acessar o Portal a usuários específicos. É recomendável que um grupo local denominado "CQDPortalUsers" ser criado para gerenciar os usuários.
  
![Implantar Painel de Qualidade da Chamada](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
Os detalhes de configuração são armazenados no Web. config localizado no diretório de físico do Portal.
  
```
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

A próxima etapa é configurar o painel do CQD. Depois que os usuários são autenticados pelo IIS, eles terão que tenha permissões de arquivo no diretório CQD para acessar o conteúdo de portal da web. É possível alterar as ACLs por meio da guia de segurança das propriedades do diretório CQD para adicionar usuários individuais ou grupos; No entanto, a abordagem recomendada é deixar as permissões de arquivo inalterada. Em vez disso, altere a configuração de IIS para usar o processo de trabalho do IIS para acessar o diretório CQD não importa qual o usuário é autenticado. 
  
> [!IMPORTANT]
> É importante apenas alterar essa configuração para o aplicativo CQD e não para os dois aplicativos de API: QoEDataService e QoERepositoryService. 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a>Configurando o acesso a arquivos para o CQD (painel)

1. Abra o Editor de configuração para CQD.
    
     ![Implantar Painel de Qualidade da Chamada](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. Na seção, escolha **system.webServer/serverRuntime**.
    
     ![Implantar Painel de Qualidade da Chamada](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. Alterar authenticatedUserOverride para **UseWorkerProcessUser**.
    
     ![Implantar Painel de Qualidade da Chamada - Editor de Configuração](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. Clique em **Aplicar** no lado direito da página.
    
## <a name="known-issues"></a>Problemas conhecidos

Em casos raros, o instalador falha para criar as configurações corretas no IIS. Alteração manual é necessária para permitir que os usuários acesse o CQD. Se os usuários estiverem tendo problemas de logon, siga estas etapas:
  
1. Abra o Gerenciador do IIS para cima e navegue para o Default Web Site.
    
     ![Implantar Painel de Qualidade da Chamada](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. Clique em "Autenticação". Se o "Autenticação anônima", "ASP.NET Impersonation", "Autenticação do formulário" e "Autenticação do Windows" não coincidem com as configurações mostradas abaixo, manualmente alterá-los para coincidir com as configurações a seguir. Todos os outros mecanismos de autenticação devem ser desabilitados.
    
     ![Implantar Painel de Qualidade da Chamada](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. Para "Autenticação do Windows", clique em configurações avançadas no lado direito.
    
     ![Implantar Painel de Qualidade da Chamada](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. Defina "Extended Protection" para aceitar e marque a caixa "autenticação de modo Kernel Enable".
    
     ![Implantar Painel de Qualidade da Chamada](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. Repita as etapas acima para cada uma das entradas "CQD", "QoEDataService" e "QoERepositoryService" abaixo "Site padrão".
    
Para ligações de porta HTTP e HTTPS, o instalador criará ligações de porta em que os números de porta padrão (porta 80 para HTTP) e a porta 443 para HTTPS. Se não houver outro site na máquina que usa essas ligações, haverá um conflito e o comportamento do IIS não pode ser previsto. Certifique-se de que não há outros sites são mapeados para portas 80 e 443 antes de instalar o CQD é a melhor maneira de evitar esse problema. 
  
Para habilitar o SSL/TLS no IIS e forçar os usuários a se conectar via HTTPS segura, em vez de HTTP:
  
1. Configurar o protocolo SSL no IIS, consulte [Configuring Secure Sockets Layer no IIS 7](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx). Depois de concluído, substitua `http` com `https`.
    
2. Para obter instruções sobre como ativar TLS as conexões do SQL Server, consulte [como habilitar a criptografia SSL para uma instância do SQL Server usando o Console de gerenciamento Microsoft ](https://support.microsoft.com/en-us/kb/316898/).
    
## <a name="cube-sync-fails"></a>Falha na sincronização de cubo

QoEMetrics podem conter alguns registros inválidos com base no relógio do usuário final. Se a diferença de horário for maior do que 60 anos, a importação de cubo falhará.
  
 Verifique os Min e Max StartTime/EndTime, usando as seleções abaixo. Procurar e excluir registros no futuro extremo passado e muito distante, pode ser desconsiderada, e eles serão interrompidos backup os processos de sincronização.
  
- Selecione MIN(StartTime) de CqdPartitionedStreamView
    
- Selecione MAX(StartTime) de CqdPartitionedStreamView
    
- Selecione MIN(EndTime) de CqdPartitionedStreamView
    
- Selecione MAX(EndTime) de CqdPartitionedStreamView
    
## <a name="post-install-tasks"></a>Tarefas pós-instalação

### <a name="importing-buildings-and-networks"></a>Importando prédios e redes

Após instalar CQD, execute as seguintes tarefas de configuração:
  
1. Definem os tipos de construção (recomendados)
    
2. Definem os tipos de propriedade de construção (recomendados)
    
3. Definem os tipos de rede (altamente recomendados)
    
4. Prédios importação (recomendado)
    
5. Sub-redes de importação (recomendados)
    
### <a name="define-building-types"></a>Definem os tipos de construção

Tipos de construção são usados para descrever as definições de prédios diferentes ou os tipos de dentro da sua organização. 
  
> [!NOTE]
> Esta etapa é opcional, mas recomendado. 
  
Exemplos
  
- Sede
    
- Escritórios remotos
    
- Local de risco de junção
    
  **Sintaxe SQL de amostra**
  
```
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

Os parâmetros BuildingTypeId e BuildingTypeDesc são necessários.
  
### <a name="define-building-ownership-types"></a>Definir os tipos de propriedade de construção

Tipos de propriedade são usados para distinguir os ativos de arrendada versus pertencentes.
  
> [!NOTE]
> Esta etapa é opcional, mas recomendado. 
  
Exemplos
  
- Não-RE Contoso concessão&amp;F
    
- Contoso concessão RE&amp;F
    
- Pertencentes a Contoso
    
- Subsidiária concedida
    
  **Sintaxe SQL de amostra**
  
```
INSERT INTO
[dbo].[CqdBuildingOwnershipType]
([OwnershipTypeId],
[OwnershipTypeDesc],
)

VALUES
(1,
'Contoso Owned',
)
```

Os parâmetros OwnershipTypeId e OwnershipTypeDesc são necessários. 
  
### <a name="define-network-names"></a>Definir os nomes de rede

Tipos de rede são usados para descrever os tipos diferentes de redes dentro da organização. Isso oferece a capacidade de filtrar (ou filtrar) tipos específicos de rede.
  
> [!NOTE]
> É altamente recomendável para definir nomes de rede, mas isso é opcional. Se você decidir não definir nomes de rede, certifique-se de que a cada entrada de CqdNetwork tem um BuildingId 0. 
  
Exemplos
  
- VPN
    
- LABORATÓRIO
    
  **Sintaxe SQL de amostra**
  
```
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

Os parâmetros NetworkNameID e NetworkName são necessários, o parâmetro NetworkType é opcional, mas recomendado.
  
### <a name="import-buildings"></a>Importação prédios

Importar prédios proporciona a capacidade de obter criando insights específicos (baixa chamadas por criar nas WiFi/com fio, etc.). 
  
> [!NOTE]
> Esta etapa é opcional, mas recomendado. 
  
Antes de importar a um novo prédio você já deve ter um BuildingKey predefinido identificado. Para fazer isso, execute o comando SQL "Selecione MAX(BuildingKey) de CqdBuilding" para identificar o valor atual e adicionar 1 para o resultado.
  
 **Sintaxe SQL de amostra**
  
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

O BuildingKey BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId parâmetros são necessários, os outros parâmetros são opcionais.
  
### <a name="import-subnets"></a>Importar sub-redes

Importar prédios proporciona a capacidade de obter criando insights específicos (baixa chamadas por criar nas WiFi/com fio, etc.). 
  
> [!NOTE]
> Esta etapa é opcional, mas recomendado. 
  
Importar sub-redes e mapeá-los para os prédios importados na última etapa. Se você decidiu não preencher NetworkName, certifique-se de que cada entrada nesta tabela usa uma NetworkNameID 0.
  
 **Sintaxe SQL de amostra**
  
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

A rede e os parâmetros UpdatedDate serão solicitados, os outros parâmetros são opcionais.
  
### <a name="optional-bssid"></a>Opcional: BSSID

Preencher informações BSSID oferece correlação de stream WiFi adicional pelo controlador ou de rádio. Esse aspecto soma filtragem por meio da criação ou sub-rede. 
  
 **Sintaxe SQL de amostra**
  
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

|**Conforme mostrado na CQD**|**Tabela CQDBssid**|**Entradas de exemplo**|
|:-----|:-----|:-----|
|AP NName  <br/> |AP  <br/> |AP1  <br/> |
|BBssid  <br/> |BSS  <br/> |00-00-00-00-00-00 (você deve usar o fformat delimitado)  <br/> |
|Controlador  <br/> |Edifício  <br/> |AP de Aruba 7  <br/> |
|Dispositivo  <br/> |ess  <br/> |Controlador1  <br/> |
|Rádio  <br/> |phy  <br/> |BGn  <br/> |
   
### <a name="processing-the-imported-data"></a>Os dados importados de processamento

Por padrão, depois de importar os dados de construção/rede ele aplicará apenas aos registros gerados depois que ponto no tempo. 
  
Para marcar todos os registros anteriores com esses novos dados, você precisará executar o procedimento armazenado do CqdUpdateBuilding, conforme mostrado a seguir: 
  
Dê a ela a data de seu primeiro registro (identificar que usando o comando Selecionar MIN(StartTime) de SQL CqdPartitionedStreamView), EndDate de amanhã, e então nulo para os valores de duas últimas.
  
Depois que os dados estão associados a dados de fluxo, o cubo SSIS precisa reprocessar todos os registros. Isso também se aplica quando em massa adicionando dados BSSID/ISP. Certifique-se de que "Processo completo" está selecionado.
  

