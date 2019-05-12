---
title: Usando o Skype para Business Server 2015 ferramenta de Stress e desempenho
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/13/2018
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93f42230-24a2-418d-9770-bf4670a9d78f
description: Para executar o Skype para Business Server 2015 ferramenta de Stress e desempenho, você vai precisa possam gerenciar usuários, contatos e perfis de usuário, configurar a ferramenta para execução e, em seguida, examine a saída ou resultados que são produzidos pela ferramenta.
ms.openlocfilehash: 750e3a85411e49bf1d9f45cbac0e634daba47d89
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904584"
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Usando o Skype para Business Server 2015 ferramenta de Stress e desempenho
 
Para executar o Skype para Business Server 2015 ferramenta de Stress e desempenho, você vai precisa possam gerenciar usuários, contatos e perfis de usuário, configurar a ferramenta para execução e, em seguida, examine a saída ou resultados que são produzidos pela ferramenta.
  
Há quatro áreas envolvidas na execução do Skype para Business Server 2015 ferramenta de Stress e desempenho (o executável é LyncPerfTool.exe):
  
- [Criar usuários e contatos](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [Configurar perfil de usuário](using-the-tool.md#BKMK_UserProfile)
    
- [Executar LyncPerfTool](using-the-tool.md#BKMK_RunTool)
    
- [Interpretando os resultados](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a>Criar usuários e contatos
<a name="BKMK_CreateUsersAndContacts"> </a>

Você precisa usar o Skype para ferramenta de provisionamento de usuário Business Server 2015 (SB 2015) (UserProvisioningTool.exe) para criar usuários e contatos para seu teste de desempenho e estresse.
  
Esta é uma lista de termos úteis que podem ser úteis à medida que você leia os tópicos:
  
- **Unidade organizacional** - unidade organizacional do Active Directory Domain Services (AD DS) (OU).
    
- **Federados / cruze Pool** - os usuários que podem se comunicar com usuários de outros serviços de mensagens instantâneas (IM).
    
- As **listas de distribuição** - ou DLs. Esses são objetos no AD DS que contêm uma lista de usuários do AD DS. Eles são usados para facilitar a comunicação entre grupos de pessoas.
    
- **Serviço de informações de local** - Skype o serviço de Business Server 2015 que, quando ele tiver habilitado e configurado por telefone, permite a recuperação de um local físico para os serviços do Enhanced 911 (E911).
    
- **Números de telefone dos EUA** - números de telefone atribuídos ao usuário além o URI do SIP que é usado para chamadas de entrada e saídas roteamento na pesquisa de número reverso (RNL).
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Criar usuários e contatos usando o UserProvisioningTool.exe

> [!NOTE]
> Antes de começar até mesmo, ter certeza absoluta que você está logado como membro do grupo de segurança Administradores de domínio para executar essa ferramenta. Você precisará fazer isso, pois você vai ser Criando usuários do Active Directory. 
  
Você precisa usar o Skype para ferramenta de provisionamento de usuário do Business Server para criar usuários e contatos para simulação de carga.
  
O **Skype para ferramenta de provisionamento de usuário do Business Server** é instalado com o pacote do **Skype para ferramenta de desempenho e estresse do Business Server** . Certifique-se de que o instalador do pacote (CapacityPlanningTool.msi) foi executado no servidor Front-End ou servidor do Standard Edition que você pretende testar.
  
Você pode iniciar o Skype para ferramenta de provisionamento de usuário do Business Server executando o arquivo UserProvisioningTool.exe (localizado em % InstalledDirectory%LyncStressAndPerfTool\LyncStress) no servidor Front-End ou no servidor Standard Edition.
  
> [!IMPORTANT]
> Quando você cria um grande número de usuários (por exemplo, 10.000 ou mais), execute o UserProvisioningTool.exe. Você precisará fazer isso porque a ferramenta será criando e configurando um *novo* AD usuários.
  
Quando a ferramenta de provisionamento de usuário for aberto, clique em configuração e selecione a configuração de carga. 
  
Para começar a configurar usuários e contatos, carregar o arquivo padrão incluído com o pacote, chamado "SampleData". Isso irá pré-preencher os campos com dados de amostra que você precisará alterar para torná-la relevantes para a sua implantação.
  
Se você tiver um arquivo XML pré-configurado que já contenha suas configurações personalizadas, você pode carregar o arquivo em vez disso. Preencha os campos na ferramenta de provisionamento de usuário, conforme descrito nas seções a seguir.
  
### <a name="to-configure-server-options"></a>Para configurar opções de servidor:

1. No campo **FQDN do Pool Front-End** , digite o nome de domínio totalmente qualificado (FQDN) do servidor Standard Edition ou pool Front-End em que você deseja hospedar os usuários.
    
2. No campo **Prefixo de nome de usuário** , digite um prefixo que você deseja usar para bust seus nomes de usuário para testes (por exemplo, "TestUser").
    
3. No campo **senha** , digite uma senha que será usada em todas as contas de usuário de teste.
    
4. No campo **Conta de domínio** , digite o nome de domínio do seu domínio do AD atual (aquela na qual você deseja criar seus usuários de teste).
    
5. No campo **Unidade organizacional** , digite o nome do domínio do AD onde você deseja criar esses usuários de teste. (Se a unidade Organizacional ainda não existir, ele será criado para você).
    
6. No campo de **código de área de telefone** , digite o código de área de três dígitos a ser usado em todas as contas de usuário de teste. Certifique-se que o código de área que você escolheu não estão em conflito com códigos de área de outros usuários no AD.
    
7. Clique para marcar a caixa de seleção **Habilitado de voz** , se você quiser permitir que os usuários de teste para o Enterprise Voice.
    
8. No campo de **Número de usuários** , dê o número total de usuários de teste que você deseja criar.
    
9. No campo de **Índice iniciar** , forneça o número inicial que vai ser usado como um sufixo para o prefixo do nome de usuário (por exemplo, o prefixo é "TestUser" e o primeiro nome será finalizado em "0" no exemplo abaixo.)
    
     ![Ferramenta mostrando a guia de criação de usuário de provisionamento de usuário.](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a>Criar um botão de usuários

Quando você clica no botão **Criar usuários** , os parâmetros de entrada que você inseriu são validados. Se houver erros de validação, você será solicitado a corrigi-los. Ou, se todos os valores corretos, os usuários iniciará que aparecem no AD (em que julgar UO especificada). Você verá uma barra de progresso na parte inferior da ferramenta conforme ele é executado. Não feche o aplicativo, enquanto a barra de progresso estiver ativa.
  
Criação de usuário leva tempo, portanto, o plano de acordo. Esse processo pode levar de alguns minutos para alguns usuários, algumas horas para um grande número de usuários.
  
Se você não tem acesso ao controlador de domínio do AD no seu ambiente de teste, você ainda pode validar a criação de usuário fazendo logon como um dos usuários no intervalo de usuários que você especificou para criar. Lembre-se utilizar o prefixo e o sufixo, juntamente com o @sipDomain como o nome de usuário. Aqui está um exemplo: <em>TestUser20@contoso.net</em> .
  
> [!NOTE]
> Se os usuários já existirem, clicando no botão Criar usuários irá atualizá-los com alterações na configuração. 
  
#### <a name="delete-users-button"></a>Excluir botão usuários

Quando você clica no botão **Excluir usuários** , os parâmetros de entrada da guia vai ser validados. Se houver erros de validação, você será solicitado a corrigi-los e se os valores de entrada estão corretos, os usuários de teste especificado serão desabilitados e excluídos do Active Directory. Novamente, uma barra de progresso será exibido na parte inferior desta guia, e você não deve fechar o aplicativo enquanto a barra de progresso estiver ativa.
  
> [!NOTE]
> Somente números de telefone dos EUA formatada são suportados. Números de telefone sempre são atribuídos a usuários e todos os usuários criados por UserProvisioningTool.exe estão habilitados para o Enterprise Voice, por padrão. Qualquer cenários que usam o número de telefone, como o atendedor automático de conferência ou chamadas UC-PSTN, usam esse número de telefone para rotear as chamadas corretamente. Por esse motivo, *cada usuário* deve ter um *número de telefone exclusivo* .
  
> [!NOTE]
> **Se você precisar criar usuários duas vezes, o comando falhará, a menos que você use um código de área diferente, ou se os usuários anteriores foram desabilitados usando o cmdlet Disable-CsUser.**
  
> [!IMPORTANT]
> Antes de criar contatos, você precisa concluir a replicação de usuário (o que é feita a partir da guia de usuários). 
  
> [!IMPORTANT]
> Se você acabou de criar os usuários, você precisará aguardar até que o Skype para replicação Business Server estiver concluído e preenche as contas de usuário no banco de dados. **Se os usuários ainda não tenham terminado replicando, você verá um erro.** Você saberá quando os usuários tem terminado replicando se já tiver iniciado o Skype para serviço de negócios 2015 Front-End Server ou executando o cmdlet Get-CsUser com êxito no último usuário do número total especificado.
  
#### <a name="contacts-creation-tab"></a>Guia de criação de contatos

Este guia lhe permite fornecer detalhes de contatos dos usuários de seu teste.
  
![Ferramenta mostrando a guia de criação de conteúdo de provisionamento de usuário.](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a>Para configurar os contatos dos usuários, faça o seguinte:

1. No campo **Contatos média por usuário** , insira o número médio de contatos para popular nas listas de contatos para cada usuário.
    
2. Se você quiser criar um número igual de contatos para cada usuário, marque a caixa de seleção **fixo** . Se você deseja variar o número de contatos criado para os usuários, desmarque essa caixa de seleção.
    
3. No campo **Grupos de contatos média por usuário** , insira o número de grupos de contatos por usuário. Esse número deve ser menor do que a **Média de contatos por usuário**.
    
4. No campo **federados / cruzar o percentual de contatos do Pool** , dê um número entre 0 e 100. Essa porcentagem dos contatos será criada com os usuários federados.
    
5. No campo **federados / cruzar o prefixo de usuário do Pool** , forneça o nome de usuário para que os usuários federados que serão adicionados às listas de contatos dos usuários locais.
    
6. No campo **federados / cruzar o domínio SIP de usuário do Pool** , forneça o nome de domínio SIP dos usuários federados.
    
7. Na guia **Criação de usuário** Verifique se que as informações estão corretas. Seus contatos serão criados dos valores na guia criação de usuário.
    
8. Clique em **Criar contatos** para começar a criação de contato. Esse processo pode levar alguns minutos. Quando ela for concluída, será exibida uma caixa de diálogo com a mensagem "operação concluída com êxito." É possível validar os contatos que foram criados fazendo logon como um usuário que foi criado a partir da guia de criação de usuário.
    
> [!NOTE]
> Depois que os contatos são criados, essa ferramenta será reiniciado todos os servidores Front-End do pool de destino. Pode levar mais tempo (até 2 horas) para servidores Front-End Iniciar, dependendo de quantos contatos foram criados por esta operação. 
  
#### <a name="distribution-list"></a>Lista de distribuição

O Skype para ferramenta de desempenho e estresse do Business Server 2015 pode simular o recurso de expansão de lista de distribuição (DL) no Skype para 2015 de negócios do cliente. Você pode ignorar esta etapa se você não pretende habilitar expansão DL na ferramenta de provisionamento de usuário.
  
![Ferramenta de provisionamento de usuário mostrando a guia de criação de listas de distribuição.](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
Na guia lista de distribuição permite que você crie DLs que a ferramenta de Stress e desempenho usará para o recurso de expansão de lista de distribuição. Antes de criar DLs, Skype para Business Server 2015 precisa ser implantado, incluindo tendo executar ForestPrep. Se isso não for feito, os atributos DL não existirá no esquema do AD, portanto, a ferramenta não poderão criar DLs.
  
### <a name="to-configure-distribution-lists"></a>Para configurar listas de distribuição:

1. No campo de **Número de listas de distribuição** , forneça o número total de DLs que você deseja criar (aqui, a recomendação é que você inicie com um valor double o número de usuários que você tiver.).
    
2. No campo **Prefixo de lista de distribuição** , digite um prefixo que terão todas as DLs criar, por exemplo *testDL* . Isso significa que, em 100 DLs, seus nomes de DL terá a seguinte aparência: testDL0, testDL1, até testDL99.
    
3. No campo **Membros mínimo em uma lista de Dist.** , insira o número mínimo de usuários para colocar em cada lista de distribuição.
    
4. No campo **Membros máximo em uma lista de Dist.** , insira o número máximo de usuários adicionem em cada lista de distribuição.
    
#### <a name="create-distribution-lists-button"></a>Criar listas de distribuição do botão

Quando você clica no botão Criar listas de distribuição, a ferramenta de consulta do Active Directory para ver se as listas de distribuição a correspondência de que prefixo e números já existirem. A ferramenta cria qualquer DL que não exista. Ao adicionar membros a estes recém-criadas em listas de distribuição, ele escolher os usuários do intervalo especificado na guia criação de usuário.
  
#### <a name="location-info-service-config-tab"></a>Guia de configuração do serviço de informações de local

O Skype para ferramenta de desempenho e estresse do Business Server 2015 também pode gerar os arquivos de configuração fictício para o serviço de informações de local. Observe que o serviço de informações de local geralmente não têm impacto significativo no desempenho nos servidores. 
  
![Ferramenta de provisionamento de usuário mostrando a guia Configuração do serviço de informações de local.](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
Se você escolher testar esse recurso, preencha os valores no formulário e clique no botão gerar os arquivos de configuração LIS, que criará. Arquivos CSV chamado:
  
- LIS_Subnet.csv
    
- LIS_Switches.csv
    
- LIS_Ports.csv
    
- LIS_WAP.csv
    
Para importar esses arquivos para o banco de dados LIS usam esses cmdlets do PowerShell:
  
- Set-CsLisSubnet
    
- Set-CsLisSwitch
    
- Set-CsLisPort
    
- Set-CsWirelessAccessPoint
    
## <a name="configure-user-profile"></a>Configurar perfil de usuário
<a name="BKMK_UserProfile"> </a>

Depois que os usuários são criados (via a ferramenta de criação de usuário), você pode configurar perfis de usuário com o Skype para a ferramenta de configuração de carga do Business Server 2015 (UserProfileGenerator.exe).
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a>Executando o Skype para ferramenta de configuração de carga do Business Server 2015

Inicie a ferramenta de configuração de carga (UserProfileGenerator.exe) e preencha as guias. Essa ferramenta cria um diretório para cada do cliente que você precisará executar simulações de seus computadores. Cada diretório de cliente vem com um script para iniciar o Skype para Business Server 2015 ferramenta de Stress e desempenho (LyncPerfTool.exe). As seções a seguir fornecerá exemplos de como preencher os campos em cada guia do Skype para ferramenta de configuração de carga do Business Server 2015.
  
> [!IMPORTANT]
> Os valores de específica do usuário usados na ferramenta de configuração de carga (UserProfileGenerator.exe) devem corresponder os valores especificados no Skype para ferramenta de criação de usuário 2015 Business Server (UserProvisioningTool.exe) para o pool. 
  
#### <a name="common-configuration-tab"></a>Guia de configuração comuns

Na guia **Configuração comum** da ferramenta de configuração de carga é mostrada abaixo. Preencha os campos da guia Configuração comum, conforme descrito nas etapas a seguir.
  
![A guia de provisionamento de usuário mostrando a guia Configuração comum.](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. No campo de **Número de máquinas disponíveis** , digite o número de computadores que você deseja usar para executar a ferramenta de Stress e desempenho (LyncPerfTool.exe). Recomendamos que você tenha um computador para cada 4500 usuários que você vai ser simulando, mas esse número pode variar se você reduzir o nível de carga, ou usar apenas um subconjunto dos recursos disponíveis da ferramenta (níveis de carregamento são definidos na guia Geral cenários).
    
2. No campo de **prefixo para nomes de usuário** , digite um prefixo para o campo de nome de usuário de todos os usuários. Para fazer logon no identificador URI (Uniform Resource) será: *UserPrefix [usuário iniciar índice … (Número de usuários-1)] @User domínio* , por exemplo, myUser009@Contoso.com.
    
3. No campo **senha para todos os usuários** , insira a senha usada durante a criação dos usuários. Se você deixe este campo em branco o nome de usuário será definido como a senha.
    
4. No campo de **Índice de início do usuário** , insira o índice do primeiro usuário a ser configurado. Você pode configurar intervalos diferentes para tipos diferentes ou níveis de carga, mas você deve executar a ferramenta de configuração de carga (UserProfileGenerator.exe) uma vez por intervalo para o qual você deseja configurar.
    
5. No campo de **Número de usuários** , insira o número total de usuários que você irá configurar.
    
6. No campo de **Usuário de domínio** , insira o domínio usado para o URI do SIP. Isso é usado para construir o URI do SIP de cada usuário fazer logon para o Skype para Business Server 2015 servidor Front-End ou servidor Standard Edition e pode ser diferente do domínio de conta.
    
7. No campo **Conta de domínio** , digite o logon no domínio AD DS.
    
8. No campo **Porcentagem de MPOP** (porcentagem de vários ponto de presença), dê um valor para o percentual de usuários que fazem logon de vários computadores ou dispositivos, por exemplo 10 por cento.
    
9. Insira o número máximo de pontos de extremidade simultâneos no campo **entrar pelo segundo (por instância)** . Esse é o máximo número de logons para seus usuários e a recomendação é uma taxa de menor que / igual a 2 por segundo (< = 2).
    
10. No campo de **Proxy de acesso ou o FQDN do Pool** , digite o nome de domínio totalmente qualificado (FQDN) do servidor que você deseja que os clientes para se conectar ao. Se os usuários fazem logon externamente, você precisará digitar o proxy de acesso. Se os usuários forem internos, dê o FQDN do seu servidor do Pool Enterprise ou Standard Edition.
    
11. No campo **porta** , insira a porta que você deseja que os usuários usem para SIP (o padrão é 5061).
    
12. Para o campo de **Configurações de servidor de rede externo** , forneça o Proxy de acesso ou FQDN do Pool e, novamente, a **porta**. Essas configurações são usadas somente para simulação de carga de pontos de extremidade externo.
    
#### <a name="general-scenarios-tab"></a>Guia de cenários gerais

![Ferramenta de configuração mostrando a guia geral de cenários de carregamento.](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
Você pode configurar os parâmetros e os níveis de carga para cada um dos cenários gerais oferecidos pelo determinando o que você deseja executar ou deixar desabilitado. Aqui estão as opções gerais:
  
> [!NOTE]
> Valores de nível de carga para todos os campos mas serviços de informações de Local são **desabilitados**, **baixa**, **média**, **alta**ou **personalizado**. Se você selecionar qualquer configuração mas desabilitados, as configurações são geradas para cada cliente. Resultados de altos no carregamento máximo com suporte no servidor. médio é 60% de carga alta; baixa é 30%. 
  
- **Mensagens instantâneas-** Isso inclui ponto a ponto e conferências; Escolha o valor apropriado para o nível de carga.
    
- **Serviços de audioconferência-** Escolha um nível de carga para conferência de áudio *apenas* . Chamadas ponto a ponto serão ser solucionadas um pouco mais tarde na seção **Cenários de voz** . Abra a guia **Avançado** para habilitar MultiView.
    
- **Compartilhamento de aplicativos-** Escolha um nível de carga para compartilhamento de aplicativos.
    
- **Colaboração de dados-** Escolha um nível de carga para colaboração de dados, que inclui a conferência de dados.
    
- **Expansão de lista de distribuição-** Clique no botão **Avançado** e preencha o campo com os mesmos valores configurados na guia DL da ferramenta de criação de usuário (UserProvisioningTool.exe). Escolha um nível de carga.
    
- **Address Book Web Query-** Esse é o serviço de pesquisa do catálogo de endereços ao invés de download de arquivo do catálogo de endereços. Se você deseja permitir isso para downloads de arquivo do catálogo de endereços, clique no botão **Avançado** e defina **EnableABSDownload** como True. Dê um valor para o nível de carga.
    
- **Serviço de grupo de resposta-** Clique no botão **Avançado** e especifique os URIs dos grupos de resposta, você já criado quando você provisionado operadores do serviço de grupo de resposta. Você deve escolher pelo menos um grupo de resposta. Para usar mais, separe os grupos de resposta com ponto e vírgula. Atualize **RGSUriSuffixStartIndex** e **RGSUriSuffixEndIndex** para os valores reais. Escolha um nível de carga.
    
- **Serviços de informações de local-** Selecione um nível de carga de habilitado ou desabilitado.
    
> [!NOTE]
> Cada um dos cenários tem um botão Avançado, localizado ao lado e um conjunto de caixas de seleção Habilitar variações para a configuração padrão. 
  
- Escolher *Ad hoc* permitirá que a ferramenta gere simulação de conferências que será criado em toda a hora.
    
- Escolher *Conf grande* significa que um cenário de conferência grande será simulado.
    
-  *Externo* informa a ferramenta para simular também usuários externos.
    
Essas caixas de seleção e botões são valores extras específicos para cada cenário e irá alterar o comportamento da ferramenta de desempenho e estresse e tornar possível a personalização.
  
Para cada cenário na guia geral de cenários (com exceção dos serviços de informações de local), se o valor de nível de carga for **personalizado**, em seguida, a taxa de conversa será calculada usando o campo correspondente na caixa de diálogo Avançado. O nome do campo pode ser diferente, dependendo do cenário, mas a descrição do campo de estado será: *Observação esse número será usada apenas se personalizado estiver selecionado no menu suspenso* .
  
Os valores de **alta**, **média**e **baixa**, alterará as taxas de conversa por modalidade alinhado com o modelo de usuário que é um equilíbrio entre todos os cenários. Se houver uma necessidade para alterar o nível de carga por modalidade devido a uma diferença no uso esperado, use uma taxa de conversa personalizado.
  
#### <a name="voice-scenarios-tab"></a>Guia de cenários de voz

Essa é a guia para a configuração de todos os seus cenários relacionadas à voz.
  
![Ferramenta de configuração de carga Guia de cenários de voz.](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
As opções são:
  
- **VoIP-** Clique no botão **Avançado** e adicione valores dos campos PhoneAreaCode e LocationProfile (plano de discagem). Você também daremos um valor para o nível de carga. Se você escolher um nível de carga para o Gateway UC/PSTN habilitada, em seguida, uma rede de telefonia pública comutada (PSTN) ou VoIP à comunicação unificada (UC) o arquivo de configuração será gerado para simular chamadas externas.
    
- **Gateway UC/PSTN-** É preciso escolher um valor de nível de carga e quando você escolhe qualquer coisa diferente de desativado, você também deve fornecer um valor para o código de área PSTN clicando no botão **Avançado** . Clique em **Adicionar** sob o servidor de mediação e o PSTN. Verifique se que você tem uma rota configurada para o código de área.
    
    > [!TIP]
    > Você pode usar ambos o Skype para painel de controle de negócios ou Skype do Shell de gerenciamento de negócios para verificar sua configuração de rota de voz. 
  
- **Atendedor de conferência-** Fornece um valor para o nível de carga. Qualquer valor diferente de Disabled permitirá que o campo **Número do telefone** . Insira o número de telefone do atendedor automático que deseja usar. Clique em **Avançado** e forneça um valor para o campo **LocationProfile** .
    
- **Chamar o serviço de estacionamento-** Aqui, fornece um nível de carga.
    
- **Servidor de mediação e PSTN-** Precisa de cada servidor de mediação que você deseja usar seu próprio simulador de PSTN. Depois que você determinou qual você vai usar para o simulador de cliente, configuração seu servidor de mediação para rotear chamadas para esse computador no simulador PSTN você configurou. Clique no botão **Adicionar** para configurar um valor para o servidor de mediação.
    
    > [!NOTE]
    > Cada cenário tem um botão Avançado, localizado ao lado dela. Caixas de diálogo Avançado contêm configurações específicas para cada cenário que alteram o comportamento da ferramenta de desempenho e estresse e habilitar personalização. gt _ para cada cenário na guia voz cenários, se o valor de nível de carga for **personalizado**, em seguida, a taxa de conversa será calculado usando-se o campo correspondente na caixa de diálogo Avançado. O nome do campo pode ser diferente, dependendo do cenário, mas a descrição do campo de estado será: *Observação esse número será usada apenas se personalizado estiver selecionado no menu suspenso* .
  
#### <a name="web-app-tab"></a>Guia de aplicativo da Web

![Ferramenta de configuração de carga, na guia Web app.](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
Web App oferece suporte a cenários de conferência por meio do servidor do Unified Communications Web API (UCWA) que está instalado em um servidor Front-End. Use a guia Web App para configurar todos os cenários relacionados ao aplicativo web. As opções são:
  
- **Configurações gerais do Web App-** Clique no botão **Configurações adicionais** e defina o **ReachTargetServerUrl** para o Pool Directory IP virtual (VIP) do pool de Front-End VIP.
    
- **Compartilhamento de aplicativos-** Selecione um valor para o nível de carga.
    
- **Colaboração de dados-** Selecione um valor para o nível de carga.
    
- **Mensagens instantâneas-** Selecione um valor para o nível de carga.
    
- **Conferência de voz-** Selecione um valor para o nível de carga.
    
> [!NOTE]
> Cada um dos cenários tem um botão **Avançado** localizado ao lado dela. Caixas de diálogo avançadas contêm valores específicos para cada cenário que irá alterar o comportamento da ferramenta de desempenho e estresse e habilitar customization.> para cada um dos cenários Web App, se o nível de carga for **personalizado**, em seguida, o valor especificado de ** ConversationsPerHour** campo é usado em vez da padrão.
  
#### <a name="mobility-tab"></a>Guia de mobilidade

Use esta guia para configurar todos os cenários relacionados a mobilidade.
  
![Guia de mobilidade de ferramenta de configuração de carga.](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
As opções aqui são:
  
- **Configurações gerais de mobilidade-** Clique em **Configurações adicionais** e defina o campo UcwaTargetServerUrl como o IP virtual de Pool de diretores (VIP) ou o VIP do pool de Front-End.
    
- **Presença e mensagens instantâneas P2P/áudio-** Selecione um valor para o nível de carga habilitar a simulação de mobilidade.
    
> [!NOTE]
> Cada um dos cenários tem um botão **Avançado** localizado ao lado dela. Caixas de diálogo avançadas contêm valores específicos para cada cenário que irá alterar o comportamento da ferramenta de desempenho e estresse e habilitar customization.> para cada um dos cenários de mobilidade, se o nível de carga for **personalizado**, em seguida, o valor especificado de ** ConversationsPerHour** campo é usado em vez da padrão.
  
#### <a name="summary-tab"></a>Guia Resumo

A guia Resumo indica quais usuários a ser usado para cada um dos cenários.
  
![Carregar a guia Resumo da ferramenta de configuração.](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
A guia Resumo indica quais usuários a ser usado para cada um dos cenários. 
  
É possível configurar manualmente os intervalos de números de usuário selecionando a caixa de seleção **Habilitar geração de intervalo de usuário personalizada** e, em seguida, clicando duas vezes no cenário na tabela que tem o intervalo de usuário que você deseja personalizar.
  
Verificar **Add (RunClient.bat) entrar atraso ao iniciar** a fim de incluir os atrasos nos arquivos de lote gerado para corresponder à taxa de entrar. Isso é útil para evitar a sobrecarga do servidor quando se entra em um grande número de usuários.
  
Clique em **Gerar arquivos** e selecione a pasta onde você deseja gerar a configuração. Uma caixa de diálogo será exibida quando os arquivos foram criados com êxito.
  
![A caixa de mensagem gerados com êxito os arquivos de configuração de carga. Basta clicar em Okey.](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a>Executar LyncPerfTool
<a name="BKMK_RunTool"> </a>

Você precisará criar usuários, contatos e cenários antes de executar o Skype para Business Server 2015 ferramenta de Stress e desempenho (LyncPerfTool.exe). Para obter detalhes sobre como usar as ferramentas para executar essas ações, consulte [criar usuários e contatos](using-the-tool.md#BKMK_CreateUsersAndContacts) e [Configurar o perfil de usuário](using-the-tool.md#BKMK_UserProfile) , anteriormente neste artigo. Executar essas ferramentas, também irá gerar um arquivo que será executado com a ferramenta de Stress e desempenho como parte de um arquivo em lotes com os parâmetros obrigatórios incluídos.
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Executando o Skype para ferramenta Business Server 2015 Stress e desempenho

A ferramenta de configuração de carga (UserProfileGenerator.exe) cria um arquivo em lotes que permite que você execute a ferramenta de Stress e desempenho (LyncPerfTool.exe) registrando contadores de desempenho e carregar o arquivo de configuração XML. O arquivo em lotes executa uma instância de LyncPerfTool.exe por arquivo de configuração. Para executar o arquivo em lotes siga estas etapas:
  
### <a name="run-the-stress-and-performance-test"></a>Executar o teste de Stress e desempenho

1. Copie a pasta com os arquivos dentro e pastas de configuração para o diretório que tenha LyncPerfTool.exe em cada computador cliente. (Por exemplo, se você tiver gerado os arquivos de configuração na pasta denominada 1.28_13.16.16, copie essa pasta para a pasta com LyncPerfTool.exe nela. Fazer isso em cada cliente.)
    
2. Navegue até a pasta do cliente e executar o script de lote **RunClient** . Você pode clicar duas vezes o arquivo em lotes no Windows Explorer, e ele será executado todos os arquivos de configuração para que o cliente. Você também pode executar o script de uma pasta de cliente usando a seguinte sintaxe:
    
   ```
   RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
   ```

Para executar a ferramenta de Stress e desempenho diretamente, abra um prompt de comando e digite o seguinte comando na linha de comando (e ao fazer isso pela primeira vez, certifique-se de registrar os contadores de desempenho `regsvr32 /i /n /s LyncPerfToolPerf.dll`, conforme mostrado na Observação neste tópico):
  
```
LyncPerfTool.exe /file:IM_client0.xml
```

Para que a ferramenta para exibir os valores no arquivo de configuração, incluem o `/displayfile` parâmetro no comando anterior, para que ele tem esta aparência:
  
```
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

Ao *final* do processo, pressione Ctrl + C.
  
> [!NOTE]
> Antes de executar a ferramenta de Stress e desempenho diretamente, você deve registrar os contadores de desempenho por meio do seguinte comando:`regsvr32 /i /n /s LyncPerfToolPerf.dll`
  
> [!NOTE]
> Cada instância da ferramenta de Stress e desempenho que iniciar imediatamente começará a assinatura em usuários, geralmente em uma taxa de um usuário por segundo. 
  
A usuário entrar taxa de pico para o pool é de cerca de 12 por segundo. Isso significa que você não deve iniciar instâncias de mais de 12 LyncPerfTool.exe ao mesmo tempo enquanto os usuários ainda estão entrando. Mil usuários levará cerca de 20 minutos totalmente entrar em um por segundo.
  
## <a name="interpreting-the-results"></a>Interpretando os resultados
<a name="BKMK_Interpret"> </a>

O Skype para ferramenta de desempenho e estresse do Business Server 2015 tem muitos contadores que podem ajudá-lo a entender o que o cliente está fazendo e se ele está encontrando problemas.
  
### <a name="client-counters"></a>Contadores do cliente

Cada instância do LyncPerfTool.exe executando tem uma instância separada dos contadores. Cada instância é nomeada por sua ID de processo. Se os clientes estiverem sobrecarregados outros problemas podem ocorrer. Para evitar esses problemas:
  
- Monitorar o uso de CPU e memória nos computadores cliente. Se a CPU está consistentemente acima 90 por cento, reduza o número de usuários.
    
- Quando o volume de memória for alto, você pode ter problemas se o arquivo da página começa a ficar sem espaço. Verifique se que a carga comprometida não está atingindo o limite no computador. Se você estiver executando em limites de memória, considere aumentar o tamanho do arquivo da página ou reduzir o número de usuários.
    
Aqui está uma lista de contadores de desempenho principais:
  
**Informações gerais**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Tempo gasto em minutos  <br/> |Tempo gasto desde o início do processo.  <br/> |
|Pontos de extremidade ativos  <br/> |Número de pontos de extremidade atualmente conectado ao servidor.  <br/> |
|Logons com falha  <br/> |Número total de falhas de entrada do ponto de extremidade.  <br/> |
|Tentativas de logon  <br/> |Número total de tentativas de entrada do ponto de extremidade.  <br/> |
|Pontos de extremidade desconectados  <br/> |Número total de pontos de extremidade que foram desconectadas.  <br/> |
   
**Informações de presença**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Chamadas SetPresence  <br/> |Número total de presença alterar tentativas. Para diferentes tipos de alterações de presença, consulte o contador de desempenho de chamadas SetPresence (tipo de presença).  <br/> |
|Respostas NNN em SetPresence  <br/> |Número total de códigos de resposta nnn recebida do servidor.  <br/> |
|Chamadas GetPresence  <br/> |Número total de tentativas de solicitação de presença get.  <br/> |
|Respostas NNN em GetPresence  <br/> |Número total de códigos de resposta nnn recebida do servidor.  <br/> |
   
**Informações do serviço de catálogo de endereços**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Downloads de arquivo completo do ABS/Delta tentadas  <br/> |Número total de completo ou delta solicitações de download de arquivo tentada.  <br/> |
|Downloads de arquivo completo do ABS/Delta sucedidas  <br/> |Número total de completo ou delta solicitações de download de arquivo tentada.  <br/> |
|Consulta à Web do catálogo de endereços contadores relacionados ao serviço  <br/> |Baixe o arquivo do catálogo de endereços contadores relacionados.  <br/> |
|Chamadas de WS ABS tentada  <br/> |Número total de solicitações de serviço Address Book Web Query tentada.  <br/> |
|Chamadas de WS ABS foi bem-sucedida  <br/> |Número total de solicitações de serviço Address Book Web Query retornou um código de resposta bem-sucedida.  <br/> |
|Falha do ABS WS chamadas  <br/> |Número total de solicitações de serviço Address Book Web Query retornou um código de resposta de erro.  <br/> |
   
> [!NOTE]
> Essa categoria inclui contadores usados para monitorar downloads de arquivo do (ABS) do serviço de catálogo de endereços e solicitações de serviço Address Book Web Query. 
  
**Informações de lista (DL) de distribuição**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Tentada de chamadas  <br/> |Número total de solicitações de serviço web de distribuição lista expansão (DLX) tentada.  <br/> |
|Chamadas bem-sucedidas  <br/> |Número total de solicitações de serviço web DLX retornou um código de resposta bem-sucedida.  <br/> |
|Chamadas com falha  <br/> |Número total de solicitações de serviço web DLX retornou um código de resposta de erro.  <br/> |
   

  
> [!NOTE]
> Os contadores de desempenho listados abaixo números de relatório para Voice todas as chamadas de IP (VoIP), incluindo chamadas para o servidor de mediação, A / V Conferencing Server, Edge Server, aplicativo grupo de resposta e atendedor automático de conferência, quando esses cenários estão habilitados. 
  
**Informações de VoIP Basic**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Chamadas ativas  <br/> |Número total de voz de entrada/saída chamadas em andamento no momento.  <br/> |
|Chamadas encerradas  <br/> |Número total de chamadas de voz de entrada/saída já foi finalizada.  <br/> |
|Chamadas recusadas  <br/> |Número total de chamadas de voz de entrada recusada.  <br/> |
|Chamadas de entrada/saída tentadas  <br/> |Número total de chamadas de voz de entrada/saída tentada.  <br/> |
|Chamadas de entrada/saída estabelecidas  <br/> |Número total de chamadas de voz de entrada/saída estabelecida.  <br/> |
|NNN recebidos de chamadas  <br/> |Número total de códigos de resposta nnn recebida do servidor.  <br/> |
|Taxa de Pass de VoIP (%)  <br/> |Total de chamadas chamadas estabelecida/Total tentadas.  <br/> |
   
**Informações de chamada de serviço de grupo de resposta**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Chamadas ativas  <br/> |Número total de chamadas ativas ao aplicativo grupo de resposta.  <br/> |
|Tentada de chamadas  <br/> |Número total de chamadas tentada.  <br/> |
   
**Informações de chamada (IM) de mensagens instantâneas**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Chamadas ativas  <br/> |Número total de chamadas de mensagens instantâneas entrada/saída em andamento.  <br/> |
|Chamadas encerradas  <br/> |Número total de chamadas de mensagens instantâneas entrada/saída já foi finalizada.  <br/> |
|NNN recebidos de chamadas  <br/> |Número total de códigos de resposta nnn recebida do servidor.  <br/> |
|Mensagens Instantâneas enviadas/recebidas  <br/> |Número total de mensagens recebidos e enviados para todas as sessões.  <br/> |
|Chamadas de entrada/saída tentadas  <br/> |Número total de entrada/saída instantâneos messaging chamadas tentada.  <br/> |
|Chamadas de entrada/saída estabelecidas  <br/> |Número total de chamadas de mensagem instantânea de entrada/saída estabelecida.  <br/> |
   
**Informações de chamada de compartilhamento de aplicativo**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Chamadas ativas  <br/> |Número total de chamadas de compartilhamento de aplicativos em andamento entrada/saída.  <br/> |
|Chamadas encerradas  <br/> |Número total de entrada/saída que compartilham aplicativos chamadas já finalizado.  <br/> |
|NNN recebidos de chamadas  <br/> |Número total de códigos de resposta nnn recebida do servidor.  <br/> |
|Chamadas de entrada/saída tentadas  <br/> |Número total de chamadas tentadas de compartilhamento de aplicativos entrada/saída.  <br/> |
|Chamadas de entrada/saída estabelecidas  <br/> |Número total de chamadas estabelecidas de compartilhamento de aplicativos entrada/saída.  <br/> |
   
**Informações de chamada CAA**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Chamadas ativas  <br/> |Número total de entrada/saída a rede telefônica pública comutada (PSTN) chamadas em andamento no momento.  <br/> |
|Chamadas encerradas  <br/> |Número total de chamadas PSTN de entrada/saída já foi finalizada.  <br/> |
|Chamadas de entrada/saída tentadas  <br/> |Número total de chamadas de entrada/saída PSTN tentada.  <br/> |
|Chamadas de entrada/saída estabelecidas  <br/> |Número total de chamadas de entrada/saída PSTN estabelecida.  <br/> |
   
**Informações de conferência**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Conferências de mensagens instantâneas ativas  <br/> |Número total de conferências de mensagem instantânea em andamento.  <br/> |
|Conferências de áudio/vídeo ativas  <br/> |Número total de em andamento de áudio/vídeo (A / V) conferências.  <br/> |
|Conferências de compartilhamento de aplicativo ativo  <br/> |Número total de conferências de compartilhamento de aplicativos em andamento.  <br/> |
|Número de participantes  <br/> |Número total de participantes de conferências conectado no momento.  <br/> |
|Falha de agenda de conferência  <br/> |Número total de falhas ao tentar agendar uma conferência.  <br/> |
|Ingressar em falha de conferência  <br/> |Número total de falhas ao tentar se conectar a uma conferência.  <br/> |
   
**Contadores de UCWA de cliente**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Número total de IMMCU ingressa sucedidas  <br/> |Número total de conferências de mensagens instantâneas reunidos.  <br/> |
|Número total de DMCU ingressa sucedidas  <br/> |Número total de A / conferências V ingressado.  <br/> |
   

