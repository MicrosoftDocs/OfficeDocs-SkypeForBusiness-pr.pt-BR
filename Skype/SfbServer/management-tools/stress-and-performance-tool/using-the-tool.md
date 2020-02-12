---
title: Usando a ferramenta de stress e desempenho do Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/13/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93f42230-24a2-418d-9770-bf4670a9d78f
description: Para executar a ferramenta de stress e desempenho do Skype for Business Server 2015, você precisará poder gerenciar os usuários, os contatos e os perfis de usuário, configurar a ferramenta para executar e, em seguida, revisar a saída ou resultados produzidos pela ferramenta.
ms.openlocfilehash: 0bdffee133e583ebaf4177d3226479838495c69f
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888860"
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Usando a ferramenta de stress e desempenho do Skype for Business Server 2015
 
Para executar a ferramenta de stress e desempenho do Skype for Business Server 2015, você precisará poder gerenciar os usuários, os contatos e os perfis de usuário, configurar a ferramenta para executar e, em seguida, revisar a saída ou resultados produzidos pela ferramenta.
  
Há quatro áreas envolvidas na execução da ferramenta de stress e desempenho do Skype for Business Server 2015 (o executável é LyncPerfTool. exe):
  
- [Criar usuários e contatos](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [Configurar perfil de usuário](using-the-tool.md#BKMK_UserProfile)
    
- [Executar LyncPerfTool](using-the-tool.md#BKMK_RunTool)
    
- [Interpretação dos resultados](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a>Criar usuários e contatos
<a name="BKMK_CreateUsersAndContacts"> </a>

Você precisa usar a ferramenta de provisionamento de usuário do Skype for Business Server 2015 (SB 2015) (UserProvisioningTool. exe) para criar usuários e contatos para seus testes de stress e desempenho.
  
Esta é uma lista de termos úteis que podem ser úteis ao ler os tópicos:
  
- **Unidade organizacional** – unidade organizacional (ou) dos serviços de domínio Active Directory (AD DS).
    
- **Pool federado/cruzado** – usuários que podem se comunicar com usuários de outros serviços de mensagens instantâneas (IM).
    
- **Listas de distribuição** ou DLS. Esses são objetos no AD DS que contêm uma lista de usuários do AD DS. Eles são usados para facilitar a comunicação entre grupos de pessoas.
    
- **Serviço de informações de localização** – o serviço do Skype for Business Server 2015 que, quando é habilitado e configurado por telefone, permite a recuperação de localização física para os serviços do 911 (E911) aprimorados.
    
- **Números de telefone dos EUA** : números de telefone atribuídos ao usuário, além do URI SIP usado para rotear chamadas de entrada e de saída em pesquisa de número reverso (RNL).
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Criar usuários e contatos usando o UserProvisioningTool. exe

> [!NOTE]
> Antes de começar, tenha certeza de que você está conectado como membro do grupo de segurança Administradores de domínio para executar essa ferramenta. Você precisa fazer isso porque vai criar usuários do Active Directory. 
  
Você precisa usar a ferramenta de provisionamento de usuário do Skype for Business Server para criar usuários e contatos para simulação de carga.
  
A **ferramenta de provisionamento de usuário do Skype for Business Server** é instalada com o pacote da **ferramenta de desempenho e carga do Skype for Business Server** . Certifique-se de que o instalador de pacotes (CapacityPlanningTool. msi) foi executado no servidor front-end ou no servidor de edição padrão que você pretende testar.
  
Você pode iniciar a ferramenta de provisionamento de usuário do Skype for Business Server executando o arquivo UserProvisioningTool. exe (localizado em% InstalledDirectory% LyncStressAndPerfTool \ LyncStress) no servidor front-end ou no servidor Standard Edition.
  
> [!IMPORTANT]
> Quando você cria um grande número de usuários (por exemplo, 10.000 ou mais), execute o UserProvisioningTool. exe. Você precisará fazer isso porque a ferramenta estará criando e configurando *novos* usuários do AD.
  
Quando a ferramenta de provisionamento de usuário abrir, clique em configuração e selecione a configuração de carga. 
  
Para começar a configurar usuários e contatos, carregue o arquivo padrão incluído no pacote, chamado "SampleData. xml". Isso irá preencher os campos com dados de exemplo que você precisará alterar para torná-los relevantes para a sua implantação.
  
Se você tiver um arquivo XML pré-configurado que já contém suas configurações personalizadas, você pode carregar esse arquivo em vez disso. Preencha os campos da ferramenta de provisionamento de usuário, conforme descrito nas seções abaixo.
  
### <a name="to-configure-server-options"></a>Para configurar as opções do servidor:

1. No campo **FQDN do pool de front-end** , digite o nome de domínio totalmente qualificado (FQDN) do servidor Standard Edition ou o pool de front-ends em que você deseja hospedar os usuários.
    
2. No campo **prefixo do nome do usuário** , digite um prefixo que você deseja usar para não usar os nomes de usuário para fins de teste (como "testuser").
    
3. No campo **senha** , digite uma senha que será usada em todas as contas de usuário de teste.
    
4. No campo **domínio da conta** , digite o nome do domínio do seu domínio atual do AD (aquele em que você deseja criar seus usuários de teste).
    
5. No campo **unidade organizacional** , digite o nome do domínio do AD em que você deseja criar esses usuários de teste. (Se a UO ainda não existir, ela será criada para você).
    
6. No campo **código de área do telefone** , digite o código de área de três dígitos a ser usado em todas as contas de usuário de teste. Certifique-se de que o código de área escolhido não entre em conflito com os códigos de área dos outros usuários no AD.
    
7. Clique para marcar a caixa de seleção **habilitado para voz** , se você quiser habilitar os usuários de teste do Enterprise Voice.
    
8. No campo **número de usuários** , forneça o número total de usuários de teste que você deseja criar.
    
9. No campo **início do índice** , forneça o número inicial que será usado como um sufixo para o prefixo do nome de usuário (por exemplo, o prefixo é "testuser", e o nome terminará em "0" no exemplo abaixo).
    
     ![Ferramenta de provisionamento de usuário mostrando a guia criação de usuário.](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a>Botão criar usuários

Quando você clica no botão **criar usuários** , os parâmetros de entrada que você digitou são validados. Se houver algum erro de validação, você será solicitado a corrigi-los. Ou, se todos os valores estiverem corretos, os usuários começarão a aparecer no AD (em qualquer UO especificada). Você verá uma barra de progresso na parte inferior da ferramenta à medida que ele é executado. Não feche o aplicativo enquanto a barra de progresso estiver ativa.
  
A criação de usuários exige tempo, portanto, planeje-se adequadamente. Esse processo pode levar alguns minutos a alguns minutos para alguns usuários, até algumas horas para um grande número de usuários.
  
Se você não tiver acesso ao controlador de domínio do AD em seu ambiente de teste, ainda poderá validar a criação de usuários fazendo logon como um dos usuários no intervalo de usuários que você especificou para criar. Lembre-se de usar o prefixo e o sufixo, juntamente com o @sipDomain como o nome do usuário. Aqui está um exemplo: <em>TestUser20@contoso.net</em> .
  
> [!NOTE]
> Se os usuários já existirem, clicar no botão criar usuários irá atualizá-los com qualquer alteração de configuração. 
  
#### <a name="delete-users-button"></a>Botão excluir usuários

Quando você clica no botão **excluir usuários** , os parâmetros de entrada da guia serão validados. Se houver erros de validação, você será solicitado a corrigi-los e, se os valores de entrada estiverem corretos, os usuários de teste especificados serão desabilitados e excluídos do Active Directory. Novamente, uma barra de progresso aparecerá na parte inferior desta guia e não será possível fechar o aplicativo enquanto a barra de progresso estiver ativa.
  
> [!NOTE]
> Só há suporte para números de telefone formatados nos EUA. Os números de telefone são sempre atribuídos aos usuários, e todos os usuários criados pelo UserProvisioningTool. exe são habilitados para o Enterprise Voice por padrão. Qualquer cenário que use o número de telefone, como atendedor automático de conferência ou chamadas UC-PSTN, use esse número de telefone para direcionar as chamadas de forma adequada. Por esse motivo, *cada usuário* deve ter um *número de telefone exclusivo* .
  
> [!NOTE]
> **Se você precisar criar usuários duas vezes, o comando falhará, a menos que você use um código de área diferente, ou se os usuários anteriores foram desabilitados usando o cmdlet Disable-CsUser.**
  
> [!IMPORTANT]
> Antes de criar contatos, você precisa primeiro completar a duplicação do usuário (que é feita na guia usuários). 
  
> [!IMPORTANT]
> Se você acabou de criar seus usuários, precisará aguardar até que a replicação do Skype for Business Server seja concluída e preencher as contas de usuário no banco de dados. **Se os usuários ainda não concluíram a replicação, você verá um erro.** Você saberá quando os usuários terminam de duplicar se o serviço de front-end do Skype for Business Server 2015 foi iniciado ou executa com êxito o cmdlet Get-CsUser no último usuário do número total especificado.
  
#### <a name="contacts-creation-tab"></a>Guia criação de contatos

Esta guia permite que você conceda aos detalhes de seus contatos os dados dos seus testes.
  
![Ferramenta de provisionamento de usuário mostrando a guia criação de conteúdo.](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a>Para configurar os contatos do usuário, faça o seguinte:

1. No campo **média de contatos por usuário** , insira o número médio de contatos a serem preenchidos nas listas de contatos de cada usuário.
    
2. Marque a caixa de seleção **fixa** se desejar criar um número igual de contatos para cada usuário. Se você quiser variar o número de contatos criados para os usuários, desmarque essa caixa de seleção.
    
3. No campo **média de grupos de contatos por usuário** , digite o número de grupos de contatos por usuário. Este número precisa ser menor do que a **média de contatos por usuário**.
    
4. No campo **porcentagem de contatos de pool federado/cruzado** , forneça um número entre 0 e 100. Esta porcentagem de contatos será criada com os usuários federados.
    
5. No campo de **prefixo de usuário federado/Cross pool** , forneça o nome de usuário para os usuários federados que serão adicionados às listas de contatos de usuários locais.
    
6. No campo **domínio SIP/usuário com vários pools** , forneça o nome de domínio SIP dos usuários federados.
    
7. Na guia **criação do usuário** certifique-se de que as informações estejam corretas. Seus contatos serão criados a partir de valores na guia criação de usuários.
    
8. Clique em **criar contatos** para iniciar a criação do contato. Esse processo pode levar alguns minutos. Após a conclusão, será exibida uma caixa de diálogo com a mensagem "operação concluída com êxito". Você pode validar os contatos que foram criados fazendo logon como um usuário criado a partir da guia criação de usuários.
    
    > [!NOTE]
    > Após a criação dos contatos, essa ferramenta reiniciará todos os servidores de front-end no pool de destino. Pode demorar mais (até 2 horas) para que os servidores front-end sejam iniciados, dependendo de quantos contatos foram criados por essa operação. 
  
#### <a name="distribution-list"></a>Lista de distribuição

A ferramenta de stress e desempenho do Skype for Business Server 2015 pode simular o recurso de expansão da lista de distribuição (DL) no cliente Skype for Business 2015. Você pode ignorar esta etapa se não quiser habilitar a expansão de DL na ferramenta de provisionamento de usuário.
  
![Ferramenta de provisionamento de usuário mostrando a guia criação da lista de distribuição.](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
A guia lista de distribuição permite que você crie DLs que a ferramenta de stress e desempenho usará para o recurso de expansão da lista de distribuição. Antes de criar DLs, o Skype for Business Server 2015 precisa ser implantado, incluindo se executarem ForestPrep. Se isso não for feito, os atributos DL não existirão no esquema de anúncios, portanto a ferramenta não poderá criar DLs.
  
### <a name="to-configure-distribution-lists"></a>Para configurar listas de distribuição:

1. No campo **número de listas de distribuição** , forneça o número total de DLS que você deseja criar (a recomendação é que você começa com um valor que é o dobro do número de usuários que você tem.).
    
2. No campo **prefixo da lista de distribuição** , insira um prefixo que todas as DLs que você criar terão, por exemplo, *testDL* . Isso significa que, às 100 DLs, seus nomes de DL terão a seguinte aparência: testDL0, testDL1, até testDL99.
    
3. No **mínimo Membros em um campo dist. List** , insira o número mínimo de usuários a serem colocados em cada DL.
    
4. No campo **máximo de membros em um campo dist. List** , insira o número máximo de usuários a serem adicionados em cada DL.
    
#### <a name="create-distribution-lists-button"></a>Botão criar listas de distribuição

Quando você clica no botão criar listas de distribuição, a ferramenta consulta o Active Directory para ver se as listas de distribuição que correspondem ao prefixo e aos números já existem. A ferramenta cria qualquer DL que ainda não existe. Ao adicionar membros a essas listas de distribuição recém-criadas, escolherá os usuários do intervalo especificado na guia criação de usuários.
  
#### <a name="location-info-service-config-tab"></a>Guia Configuração do serviço de informações de localização

A ferramenta de desempenho e carga útil do Skype for Business Server 2015 também pode gerar arquivos de configuração fictícios para o serviço de informações de localização. Observe que o serviço de informações de localização geralmente não tem impacto significativo no desempenho dos servidores. 
  
![Ferramenta de provisionamento do usuário mostrando a guia Configuração do serviço de informações de localização.](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
Se você optar por testar esse recurso, preencha os valores no formulário e clique no botão Generate LIS config files, que será criado. Arquivos CSV chamados:
  
- LIS_Subnet. csv
    
- LIS_Switches. csv
    
- LIS_Ports. csv
    
- LIS_WAP. csv
    
Para importar esses arquivos para o banco de dados LIS, use estes cmdlets do PowerShell:
  
- Set-CsLisSubnet
    
- Set-CsLisSwitch
    
- Set-CsLisPort
    
- Set-CsWirelessAccessPoint
    
## <a name="configure-user-profile"></a>Configurar perfil de usuário
<a name="BKMK_UserProfile"> </a>

Após a criação dos usuários (por meio da ferramenta de criação de usuários), você pode configurar perfis de usuário com a ferramenta de configuração de carregamento do Skype for Business Server 2015 (UserProfileGenerator. exe).
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a>Executando a ferramenta de configuração de carga do Skype for Business Server 2015

Inicie a ferramenta de configuração de carregamento (UserProfileGenerator. exe) e preencha as guias. Essa ferramenta cria um diretório para cada um dos computadores cliente que você precisará para executar suas simulações. Cada diretório do cliente vem com um script para iniciar a ferramenta de stress e desempenho do Skype for Business Server 2015 (LyncPerfTool. exe). As seções a seguir fornecerão exemplos de como preencher os campos em cada guia da ferramenta de configuração de carregamento do Skype for Business Server 2015.
  
> [!IMPORTANT]
> Os valores específicos de usuário usados na ferramenta de configuração de carregamento (UserProfileGenerator. exe) devem coincidir com os valores especificados na ferramenta de criação de usuários do Skype for Business Server 2015 (UserProvisioningTool. exe) para o pool. 
  
#### <a name="common-configuration-tab"></a>Guia configuração comum

A guia **configuração comum** da ferramenta de configuração de carga é mostrada abaixo. Preencha os campos da guia configuração comum, conforme descrito nas etapas a seguir.
  
![A guia provisionamento de usuário mostrando a guia configuração comum.](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. No campo **número de máquinas disponíveis** , digite o número de computadores que você deseja usar para executar a ferramenta stress and Performance (LyncPerfTool. exe). Recomendamos que você tenha um computador para cada um dos usuários do 4500 que você simulará, mas esse número poderá variar se você reduzir o nível de carga ou usar apenas um subconjunto de recursos disponíveis da ferramenta (os níveis de carga são definidos na guia cenários gerais).
    
2. No campo **prefixo para nomes de usuário** , insira um prefixo para o campo nome de usuário de todos os usuários. Para fazer logon no URI (Uniform Resource Identifier) será: *userprefix [índice de início do usuário... (Número de usuários-1)] @User domínio* , por exemplo, myUser009@Contoso.com.
    
3. No campo **senha para todos os usuários** , insira a senha usada durante a criação dos usuários. Se você deixar este campo vazio, o nome de usuário será definido como a senha.
    
4. No campo de **índice inicial do usuário** , digite o índice do primeiro usuário a ser configurado. Você pode configurar intervalos diferentes para tipos ou níveis diferentes de carga, mas é necessário executar a ferramenta de configuração de carregamento (UserProfileGenerator. exe) uma vez por o intervalo que você deseja configurar.
    
5. No campo **número de usuários** , digite o número total de usuários que você vai configurar.
    
6. No campo **domínio do usuário** , insira o domínio usado para o URI do SIP. Isso é usado para construir o URI SIP de cada usuário para fazer logon no servidor front-end do Skype for Business Server 2015 ou no servidor Standard Edition, e pode ser diferente do domínio da conta.
    
7. No campo **domínio da conta** , insira o logon de domínio do AD DS.
    
8. No campo **porcentagem** (ponto de presença múltiplo) MPOP, forneça um valor para a porcentagem de usuários que se conectaram de várias máquinas ou dispositivos, por exemplo, 10%.
    
9. Digite o número máximo de pontos de extremidade simultâneos no campo **entrar por segundo (por instância)** . Esse é o número máximo de logs para seus usuários, e a recomendação é uma taxa de menos de/igual a 2 por segundo (<= 2).
    
10. No campo **proxy do Access ou FQDN do pool** , digite o nome de domínio totalmente qualificado (FQDN) do servidor ao qual você deseja que os clientes se conectem. Se os usuários estiverem fazendo logon externamente, você precisará digitar o proxy de acesso. Se os usuários forem internos, forneça o FQDN do seu pool da empresa ou do servidor Standard Edition.
    
11. No campo **porta** , insira a porta que você deseja que os usuários usem para SIP (o padrão aqui é 5061).
    
12. Para o campo **configurações do servidor de rede externo** , forneça o proxy de acesso ou o FQDN do pool e, novamente, a **porta**. Essas configurações são usadas apenas para simulação de carga de pontos de extremidade externos.
    
#### <a name="general-scenarios-tab"></a>Guia cenários gerais

![Ferramenta de configuração de carregamento mostrando a guia cenários gerais.](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
Você pode configurar os níveis de carga e os parâmetros para cada um dos cenários gerais oferecidos determinando o que você deseja executar ou deixar desabilitado. Aqui estão suas opções gerais:
  
> [!NOTE]
> Os valores de nível de carga para todos os campos, mas os serviços de informações locais são **desabilitados**, **baixados**, **médios**, **altos**ou **personalizados**. Se você selecionar qualquer configuração, mas desativada, as configurações serão geradas para cada cliente. Resultados altos na carga máxima suportada no servidor; médio é 60% de alta carga; baixo é 30%. 
  
- **Mensagens instantâneas-** Isso inclui ponto a ponto e conferência; Escolha o valor apropriado para nível de carga.
    
- **Conferência de áudio-** Escolha um nível de carga *somente* para a conferência de áudio. As chamadas ponto a ponto serão solucionadas mais tarde na seção **cenários de voz** . Abrir a guia **avançado** para habilitar o MultiView.
    
- **Compartilhamento de aplicativos –** Escolha um nível de carga para compartilhamento de aplicativos.
    
- **Colaboração de dados-** Escolha um nível de carga para a colaboração de dados, que inclui a conferência de dados.
    
- **Expansão da lista de distribuição-** Clique no botão **avançado** e preencha o campo com os mesmos valores configurados na guia DL da ferramenta de criação de usuários (UserProvisioningTool. exe). Escolha um nível de carga.
    
- **Consulta à Web do catálogo de endereços-** Este é o serviço de pesquisa de catálogo de endereços em vez do download do arquivo do catálogo de endereços. Se você quiser habilitar isso para downloads de arquivo do catálogo de endereços, clique no botão **avançado** e defina **EnableABSDownload** como verdadeiro. Forneça um valor para o nível de carga.
    
- **Serviço de grupo de resposta-** Clique no botão **avançado** e especifique os URIs dos grupos de resposta que você já criou ao provisionar agentes de serviço de grupo de resposta. Você deve escolher pelo menos um grupo de resposta. Para usar mais, separe os grupos de resposta com ponto-e-vírgula. Atualize **RGSUriSuffixStartIndex** e **RGSUriSuffixEndIndex** para os valores reais. Escolha um nível de carga.
    
- **Serviços de informações de localização-** Selecione um nível de carga habilitado ou desabilitado.
    
> [!NOTE]
> Cada um dos cenários tem um botão Avançado localizado ao lado dele e um conjunto de caixas de seleção que permitem variações para a configuração padrão. 
  
- Escolher *ad-hoc* permitirá que a ferramenta gere simulação de conferências que serão criadas em toda a hora.
    
- Escolher *grande conf* significa que um cenário de conferência grande será simulado.
    
-  *Externo* informa à ferramenta para também simular usuários externos.
    
Esses botões e caixas de seleção são valores adicionais específicos de cada cenário e alterarão o comportamento da ferramenta de stress e desempenho e tornarão a personalização possível.
  
Para cada cenário na guia cenários gerais (exceto para serviços de informações de localização), se o valor do nível de carga for **personalizado**, a taxa de conversa será calculada usando o campo correspondente na caixa de diálogo avançado. O nome do campo pode ser diferente, dependendo do cenário, mas a descrição do campo entrará: *Observação esse número será usado apenas se personalizado estiver selecionado no menu suspenso* .
  
Os valores **alto**, **médio**e **baixo**, alterarão as tarifas de conversa por modalidade em linha com o modelo de usuário que é o saldo de todos os cenários. Se houver necessidade de alterar o nível de carga por modalidade devido a uma diferença no uso esperado, use uma taxa de conversa personalizada.
  
#### <a name="voice-scenarios-tab"></a>Guia cenários de voz

Esta é a guia para configuração de todos os cenários relacionados a voz.
  
![Ferramenta de configuração de carga Guia de cenários de voz.](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
Suas opções são:
  
- **VoIP-** Clique no botão **avançado** e adicione valores para os campos PhoneAreaCode e LocationProfile (plano de discagem). Você também terá um valor para o nível de carga. Se você escolher um nível de carga para o gateway de VoIP ou de UC/PSTN habilitado, um arquivo de configuração de rede telefônica pública comutada (PSTN) para a comunicação unificada (UC) será gerado para simular chamadas externas.
    
- **Gateway UC/PSTN-** Você precisa escolher um valor de nível de carga e, quando escolher algo diferente de desabilitado, também é necessário fornecer um valor para o código de área PSTN clicando no botão **avançado** . Clique em **Adicionar** no servidor de mediação e na PSTN. Verifique se você tem uma rota configurada para o código de área.
    
    > [!TIP]
    > Você pode usar o painel de controle do Skype for Business ou o Shell de gerenciamento do Skype for Business para verificar a configuração da sua rota de voz. 
  
- **Atendedor de conferência-** Forneça um valor para o nível de carga. Qualquer valor diferente de Disabled habilitará o campo de **número de telefone** . Digite o número de telefone do atendedor automático que você deseja usar. Clique em **avançado** e dê um valor para o campo **LocationProfile** .
    
- **Serviço de estacionamento de chamadas-** Aqui, forneça um nível de carga.
    
- **Servidor de mediação e PSTN-** Cada servidor de mediação que você deseja usar precisa do seu próprio simulador PSTN. Depois de determinar qual cliente você vai usar para o simulador, configure o servidor de mediação para direcionar chamadas para esse computador no simulador PSTN que você configurou. Clique no botão **Adicionar** para configurar um valor para o servidor de mediação.
    
    > [!NOTE]
    > Cada cenário tem um botão Avançado localizado ao lado dele. Caixas de diálogo avançadas contêm configurações específicas de cada cenário que alteram o comportamento da ferramenta de stress e desempenho e permitem a personalização. > para cada cenário na guia cenários de voz, se o valor do nível de carga for **personalizado**, a taxa de conversa será calculada usando o campo correspondente na caixa de diálogo avançado. O nome do campo pode ser diferente, dependendo do cenário, mas a descrição do campo entrará: *Observação esse número será usado apenas se personalizado estiver selecionado no menu suspenso* .
  
#### <a name="web-app-tab"></a>Guia do aplicativo Web

![Ferramenta de configuração de carregamento, guia do aplicativo Web.](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
O aplicativo Web dá suporte a cenários de conferência por meio do servidor UCWA (Unified Communication Web API) instalado em um servidor front-end. Use a guia do aplicativo Web para configurar todos os cenários relacionados ao aplicativo Web. As opções são:
  
- **Configurações gerais do aplicativo Web-** Clique no botão **configurações adicionais** e defina o **REACHTARGETSERVERURL** para o VIP (IP virtual) do pool de diretórios do VIP do pool de front-ends.
    
- **Compartilhamento de aplicativos –** Selecione um valor para nível de carga.
    
- **Colaboração de dados-** Selecione um valor para nível de carga.
    
- **Mensagens instantâneas-** Selecione um valor para nível de carga.
    
- **Conferência de voz-** Selecione um valor para nível de carga.
    
> [!NOTE]
> Cada um dos cenários tem um botão **avançado** localizado ao lado dele. As caixas de diálogo avançadas contêm valores específicos para cada cenário que alteram o comportamento da ferramenta de stress e desempenho e permitem a personalização. > para cada um dos cenários do aplicativo Web, se o nível de carga for **personalizado**, o valor especificado no campo **ConversationsPerHour** será usado em vez do padrão.
  
#### <a name="mobility-tab"></a>Guia Mobility

Use esta guia para configurar todos os cenários relacionados à mobilidade.
  
![Carregar a guia de mobilidade da ferramenta de configuração.](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
As opções são:
  
- **Configurações gerais de mobilidade-** Clique em **configurações adicionais** e defina o campo UcwaTargetServerUrl para o VIP (IP virtual) do pool diretor ou o VIP do pool de front-end.
    
- **Presença e mensagens instantâneas P2P/áudio-** Selecione um valor para o nível de carga para habilitar a simulação de mobilidade.
    
> [!NOTE]
> Cada um dos cenários tem um botão **avançado** localizado ao lado dele. As caixas de diálogo avançadas contêm valores específicos para cada cenário que alteram o comportamento da ferramenta de stress e desempenho e permitem a personalização. > para cada um dos cenários de mobilidade, se o nível de carga for **personalizado**, o valor especificado no campo **ConversationsPerHour** será usado em vez do padrão.
  
#### <a name="summary-tab"></a>Guia Resumo

A guia Resumo indica quais usuários usar para cada um dos cenários.
  
![Guia Resumo da ferramenta de configuração carregar.](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
A guia Resumo indica quais usuários usar para cada um dos cenários. 
  
É possível configurar manualmente intervalos de números de usuário, marcando a caixa de seleção **habilitar geração de intervalo de usuários personalizados** e clicando duas vezes no cenário na tabela que contém o intervalo de usuários que você deseja personalizar.
  
Verifique **(RunClient. bat) adicione o atraso de entrada ao iniciar** para incluir atrasos nos arquivos em lote gerados para que correspondam à taxa de conexão. Isso é útil para evitar a sobrecarga do servidor ao entrar em um grande número de usuários.
  
Clique em **gerar arquivos** e selecione a pasta onde deseja gerar a configuração. Uma caixa de diálogo será exibida quando os arquivos tiverem sido criados com êxito.
  
![A caixa de mensagem ' carregar arquivos de configuração gerados com êxito '. Basta clicar em OK.](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a>Executar LyncPerfTool
<a name="BKMK_RunTool"> </a>

Você precisará criar usuários, contatos e cenários antes de executar a ferramenta de stress e desempenho do Skype for Business Server 2015 (LyncPerfTool. exe). Para obter detalhes sobre como usar as ferramentas para executar essas ações, consulte [criar usuários e contatos](using-the-tool.md#BKMK_CreateUsersAndContacts) e [Configurar o perfil de usuário](using-the-tool.md#BKMK_UserProfile) anteriormente neste artigo. Executar essas ferramentas também gerará um arquivo que será executado com a ferramenta stress e performance como parte de um arquivo em lote com os parâmetros necessários incluídos.
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Executando a ferramenta de stress e desempenho do Skype for Business Server 2015

A ferramenta de configuração de carregamento (UserProfileGenerator. exe) cria um arquivo em lotes que permite que você execute a ferramenta de stress e desempenho (LyncPerfTool. exe) registrando contadores de desempenho e carregando o arquivo de configuração XML. O arquivo em lote executa uma instância do LyncPerfTool. exe por arquivo de configuração. Para executar o arquivo em lotes, siga estas etapas:
  
### <a name="run-the-stress-and-performance-test"></a>Executar o teste de carga e desempenho

1. Copie a pasta com os arquivos e pastas de configuração no diretório que tem o LyncPerfTool. exe em cada computador cliente. (Por exemplo, se você gerou os arquivos de configuração na pasta denominada 1.28 _ 13.16.16, copie essa pasta para a pasta com LyncPerfTool. exe. Faça isso em cada cliente.)
    
2. Navegue até a pasta cliente e execute o script em lotes **RunClient** . Você pode clicar duas vezes no arquivo em lotes no Windows Explorer e ele executará todos os arquivos de configuração desse cliente. Você também pode executar o script a partir de uma pasta de cliente usando a seguinte sintaxe:
    
   ```console
   RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
   ```

Para executar a ferramenta stress and Performance diretamente, abra um prompt de comando e digite o seguinte comando na linha de comando (e, quando fizer isso pela primeira vez, certifique-se de registrar os `regsvr32 /i /n /s LyncPerfToolPerf.dll`contadores de desempenho, conforme mostrado na observação mais adiante neste tópico):
  
```console
LyncPerfTool.exe /file:IM_client0.xml
```

Para que a ferramenta exiba os valores no arquivo de configuração, inclua o `/displayfile` parâmetro no comando anterior para que ele tenha a seguinte aparência:
  
```console
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

Para *encerrar* o processo, pressione CTRL + C.
  
> [!NOTE]
> Antes de executar a ferramenta stress and Performance diretamente, você deve registrar os contadores de desempenho por meio do seguinte comando:`regsvr32 /i /n /s LyncPerfToolPerf.dll`
  
> [!NOTE]
> Cada ocorrência da ferramenta de stress e desempenho iniciada imediatamente começará a entrar em usuários, geralmente a uma taxa de um usuário por segundo. 
  
A taxa de conexão de usuários de pico para o pool é cerca de 12 a cada segundo. Isso significa que você não deve iniciar mais de 12 instâncias do LyncPerfTool. exe ao mesmo tempo enquanto os usuários ainda estão entrando. 1000 os usuários demorarão cerca de 20 minutos para se conectarem por conta única por segundo.
  
## <a name="interpreting-the-results"></a>Interpretação dos resultados
<a name="BKMK_Interpret"> </a>

A ferramenta de stress e desempenho do Skype for Business Server 2015 tem muitos contadores que podem ajudá-lo a entender o que o cliente está fazendo e se ele está encontrando problemas.
  
### <a name="client-counters"></a>Contadores de cliente

Cada instância de LyncPerfTool. exe em execução tem uma instância separada dos contadores. Cada instância é nomeada pela ID do processo. Se os clientes forem sobrecarregados, outros problemas poderão ocorrer. Para evitar estes problemas:
  
- Monitore o uso da CPU e da memória nos computadores cliente. Se a CPU estiver consistentemente acima de 90%, reduza o número de usuários.
    
- Quando o espaço da memória for alto, você poderá ter problemas se o arquivo de página começar a ficar sem espaço. Verifique se a carga comprometida não está atingindo o limite do computador. Se você estiver executando limites de memória, considere aumentar o tamanho do arquivo da página ou reduzir o número de usuários.
    
Aqui está uma lista de contadores chave de desempenho:
  
**Informações gerais**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Tempo gasto em minutos  <br/> |Tempo gasto desde o início do processo.  <br/> |
|Pontos de extremidade ativos  <br/> |Número de pontos de extremidade conectados ao servidor no momento.  <br/> |
|Logons com falha  <br/> |Número total de falhas de entrada de ponto de extremidade.  <br/> |
|Tentativas de logon  <br/> |Número total de tentativas de entrada no ponto de extremidade.  <br/> |
|Pontos de extremidade desconectados  <br/> |Número total de pontos de extremidade desconectados.  <br/> |
   
**Informações de presença**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Chamadas de presença  <br/> |Número total de tentativas de alteração de presença. Para diferentes tipos de alterações de presença, consulte o contador de desempenho de chamadas de presença (tipo de presença).  <br/> |
|Respostas de NNN para setpresence  <br/> |Número total de códigos de resposta de nnn recebidos do servidor.  <br/> |
|Chamadas de getpresence  <br/> |Número total de tentativas de obter solicitação de presença.  <br/> |
|Respostas NNN para getpresence  <br/> |Número total de códigos de resposta de nnn recebidos do servidor.  <br/> |
   
**Informações do serviço de catálogo de endereços**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Tentativas de download de arquivo completo/Delta da ABS  <br/> |Número total de solicitações de download de arquivos completas ou Delta tentadas.  <br/> |
|Downloads de arquivo completo/Delta do ABS bem-sucedido  <br/> |Número total de solicitações de download de arquivos completas ou Delta tentadas.  <br/> |
|Contadores relacionados ao serviço de consulta na Web do catálogo de endereços  <br/> |Contadores relacionados ao download de arquivos do catálogo de endereços.  <br/> |
|Chamadas de WS WS tentadas  <br/> |Número total de tentativas de solicitações de serviço de consulta à Web do catálogo de endereços.  <br/> |
|Chamadas do WS para ABS bem-sucedidas  <br/> |Número total de solicitações de serviço de consulta à Web do catálogo de endereços que retornaram um código de resposta bem-sucedido.  <br/> |
|Falha nas chamadas ABS WS  <br/> |Número total de solicitações de serviço de consulta à Web do catálogo de endereços que retornaram um código de resposta de erro.  <br/> |
   
> [!NOTE]
> Esta categoria inclui contadores usados para monitorar downloads de arquivos do serviço de catálogo de endereços (ABS) e catálogo de endereços da Web consulta de serviço. 
  
**Informações de lista de distribuição (DL)**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Chamadas tentadas  <br/> |Número total de solicitações de serviço Web de expansão da lista de distribuição (DLX) tentadas.  <br/> |
|Chamadas com êxito  <br/> |Número total de solicitações de serviço Web DLX que retornaram um código de resposta bem-sucedido.  <br/> |
|Falha nas chamadas  <br/> |Número total de solicitações de serviço Web DLX que retornaram um código de resposta de erro.  <br/> |
   

  
> [!NOTE]
> Os contadores de desempenho listados abaixo numeram os números de todas as chamadas de voz sobre IP (VoIP), incluindo chamadas para servidor de mediação, servidor de conferência A/V, servidor de borda, aplicativo de grupo de resposta e atendedor automático de conferência, quando esses cenários são habilitados. 
  
**Informações básicas de VoIP**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Chamadas ativas  <br/> |Número total de chamadas de voz de entrada/saída em andamento no momento.  <br/> |
|Chamadas terminadas  <br/> |Número total de chamadas de voz de entrada/saída já terminadas.  <br/> |
|Chamadas recusadas  <br/> |Número total de chamadas de voz recebidas recusadas.  <br/> |
|Tentativa de fazer chamadas de entrada/saída  <br/> |Número total de chamadas de voz de entrada/saída tentadas.  <br/> |
|Chamadas de entrada/saída estabelecidas  <br/> |Número total de chamadas de voz de entrada/saída estabelecidas.  <br/> |
|Chamadas recebidas NNN  <br/> |Número total de códigos de resposta de nnn recebidos do servidor.  <br/> |
|Taxa de aprovação de VoIP (%)  <br/> |Total de chamadas estabelecidas/total de chamadas tentadas.  <br/> |
   
**Informações de chamada do serviço de grupo de resposta**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Chamadas ativas  <br/> |Número total de chamadas ativas para o aplicativo de grupo de resposta.  <br/> |
|Chamadas tentadas  <br/> |Número total de chamadas tentadas.  <br/> |
   
**Informações de chamada de mensagens instantâneas (IM)**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Chamadas ativas  <br/> |Número total de chamadas de mensagens instantâneas de entrada/saída contínuas.  <br/> |
|Chamadas terminadas  <br/> |Número total de chamadas de entrada/saída de mensagens instantâneas já terminadas.  <br/> |
|Chamadas recebidas NNN  <br/> |Número total de códigos de resposta de nnn recebidos do servidor.  <br/> |
|Mensagens INSTANTÂNEAs recebidas/enviadas  <br/> |Número total de mensagens recebidas ou enviadas para todas as sessões.  <br/> |
|Tentativa de fazer chamadas de entrada/saída  <br/> |Número total de tentativas de entrada/saída de mensagens instantâneas feitas.  <br/> |
|Chamadas de entrada/saída estabelecidas  <br/> |Número total de chamadas de entrada/saída de mensagens instantâneas estabelecidas.  <br/> |
   
**Informações de chamada de compartilhamento de aplicativo**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Chamadas ativas  <br/> |Número total de chamadas de compartilhamento de aplicativo de entrada/saída contínuas.  <br/> |
|Chamadas terminadas  <br/> |Número total de chamadas de compartilhamento de aplicativo de entrada/saída já terminadas.  <br/> |
|Chamadas recebidas NNN  <br/> |Número total de códigos de resposta de nnn recebidos do servidor.  <br/> |
|Tentativa de fazer chamadas de entrada/saída  <br/> |Número total de chamadas de compartilhamento de aplicativo de entrada/saída tentadas.  <br/> |
|Chamadas de entrada/saída estabelecidas  <br/> |Número total de chamadas de compartilhamento de aplicativo de entrada/saída estabelecidas.  <br/> |
   
**Informações de chamada do CAA**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Chamadas ativas  <br/> |Número total de chamadas em PSTN (rede telefônica pública comutada) de entrada/saída em andamento no momento.  <br/> |
|Chamadas terminadas  <br/> |Número total de chamadas PSTN de entrada/saída já terminadas.  <br/> |
|Tentativa de fazer chamadas de entrada/saída  <br/> |Número total de chamadas de entrada PSTN de entrada/saída tentadas.  <br/> |
|Chamadas de entrada/saída estabelecidas  <br/> |Número total de chamadas PSTN de entrada/saída estabelecidas.  <br/> |
   
**Informações de conferência**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Conferências de mensagens instantâneas ativas  <br/> |Número total de conferências de mensagens instantâneas em andamento.  <br/> |
|Conferências de áudio/vídeo ativas  <br/> |Número total de conferências contínuas de áudio/vídeo (A/V).  <br/> |
|Conferências de compartilhamento de aplicativos ativos  <br/> |Número total de conferências de compartilhamento de aplicativos contínuas.  <br/> |
|Número de participantes  <br/> |Número total de participantes atualmente conectados a conferências.  <br/> |
|Falha no cronograma da conferência  <br/> |Número total de falhas ao tentar agendar uma conferência.  <br/> |
|Ingressar na falha na conferência  <br/> |Número total de falhas ao tentar se conectar a uma conferência.  <br/> |
   
**Contadores do cliente UCWA**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Número total de junções de IMMCU bem-sucedida  <br/> |Número total de conferências de mensagens instantâneas Unidas.  <br/> |
|Número total de junções de DMCU bem-sucedida  <br/> |Número total de conferências de A/V Unidas.  <br/> |
   

