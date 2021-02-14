---
title: Usando a Ferramenta de Stress and Performance do Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Para executar a Ferramenta de Stress and Performance do Skype for Business Server 2015, você precisará gerenciar usuários, contatos e perfis de usuário, configurar a ferramenta para execução e revisar os resultados produzidos pela ferramenta.
ms.openlocfilehash: e008a85d22753a4e649da8501bd387675bb9b536
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814941"
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Usando a Ferramenta de Stress and Performance do Skype for Business Server 2015
 
Para executar a Ferramenta de Stress and Performance do Skype for Business Server 2015, você precisará gerenciar usuários, contatos e perfis de usuário, configurar a ferramenta para execução e revisar os resultados produzidos pela ferramenta.
  
Há quatro áreas envolvidas na execução da Ferramenta de Stress and Performance do Skype for Business Server 2015 (o executável é LyncPerfTool.exe):
  
- [Criar Usuários e Contatos](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [Configurar Perfil de Usuário](using-the-tool.md#BKMK_UserProfile)
    
- [Executar LyncPerfTool](using-the-tool.md#BKMK_RunTool)
    
- [Interpretar os resultados](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a>Criar Usuários e Contatos
<a name="BKMK_CreateUsersAndContacts"> </a>

Você precisa usar a Ferramenta de Provisionamento de Usuários (UserProvisioningTool.exe) do Skype for Business Server 2015 (SB 2015) para criar usuários e contatos para seu teste de estresse e desempenho.
  
Esta é uma lista de termos úteis que podem ser úteis conforme você lê nos tópicos:
  
- **Unidade Organizacional** - A unidade organizacional (UO) dos Serviços de Domínio Active Directory (AD DS).
    
- **Federado/Pool Cruzado** - Usuários que podem se comunicar com usuários de outros serviços de mensagens instantâneas (IM).
    
- **Listas de Distribuição** - ou DLs. São objetos no AD DS que contêm uma lista de usuários do AD DS. Eles são usados para facilitar as comunicações entre grupos de pessoas.
    
- **Serviço** de Informações de Local - O serviço do Skype for Business Server 2015 que, quando habilitado e configurado por telefone, permite a recuperação do local físico para serviços do Enhanced 911 (E911).
    
- Números **de** Telefone dos EUA - Números de telefone atribuídos ao usuário, além do URI do SIP usado para rotear chamadas de entrada e saída na RNL (RNL).
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Criar Usuários e Contatos usando o UserProvisioningTool.exe

> [!NOTE]
> Antes de começar, certifique-se de estar conectado como membro do grupo de segurança Administradores de Domínio para executar essa ferramenta. Você precisa fazer isso, pois criará usuários do Active Directory. 
  
Você precisa usar a Ferramenta de Provisionamento de Usuários do Skype for Business Server para criar usuários e contatos para simulação de carga.
  
A **Ferramenta de Provisionamento de Usuários** do Skype for Business Server é instalada com o pacote da Ferramenta de Stress and Performance do Skype for Business **Server.** Certifique-se de que o instalador de pacote (CapacityPlanningTool.msi) foi executado no Servidor front-end ou no servidor Standard Edition que você pretende testar.
  
Você pode iniciar a Ferramenta de Provisionamento de Usuário do Skype for Business Server executando o arquivo UserProvisioningTool.exe (localizado em %InstalledDirectory%LyncStressAndPerfTool\LyncStress) no Servidor front-end ou no servidor Standard Edition.
  
> [!IMPORTANT]
> Quando você cria um grande número de usuários (por exemplo, 10.000 ou mais), execute o UserProvisioningTool.exe. Você precisará fazer isso porque a ferramenta criará e configurará novos  *usuários*  do AD.
  
Quando a Ferramenta de Provisionamento do Usuário for aberta, clique em Configuração e selecione a Configuração de Carregamento. 
  
Para começar a configurar usuários e contatos, carregue o arquivo padrão incluído no pacote, chamado "SampleData.xml". Isso pré-fará com que os campos com dados de exemplo que você precisará alterar para torná-los relevantes para sua implantação.
  
Se você tiver um arquivo XML pré-configurado que já contém suas configurações personalizadas, poderá carregar esse arquivo. Preencha os campos na Ferramenta de Provisionamento de Usuário, conforme descrito nas seções abaixo.
  
### <a name="to-configure-server-options"></a>Para configurar opções de servidor:

1. No campo FQDN do Pool de **Front-End,** digite o nome de domínio totalmente qualificado (FQDN) do servidor Standard Edition ou o pool de Front-End onde você deseja hospedar os usuários.
    
2. No campo **Prefixo de** Nome de Usuário, digite um prefixo que você deseja usar para usar para testar os nomes de usuário (como "TestUser").
    
3. No campo **Senha,** digite uma senha que será usada em todas as contas de usuário de teste.
    
4. No campo **Domínio da** Conta, digite o nome de domínio do seu domínio atual do AD (aquele no qual você deseja criar seus usuários de teste).
    
5. No campo **Unidade Organizacional,** digite o nome do domínio do AD onde você deseja criar esses usuários de teste. (Se a UO ainda não existir, ela será criada para você).
    
6. No campo **Código de Área de** Telefone, digite o código de área de três dígitos a ser usado em todas as contas de usuário de teste. Certifique-se de que o código de área escolhido não entre em conflito com os códigos de área de outros usuários no AD.
    
7. Clique para marcar a **caixa de seleção Habilitar Voz,** se quiser habilitar os usuários de teste para o Enterprise Voice.
    
8. No campo **Número de Usuários,** dê o número total de usuários de teste que você deseja criar.
    
9. No  campo Índice inicial, dê o número inicial que será usado como sufixo para o prefixo de nome de usuário (por exemplo, o prefixo é "TestUser" e o primeiro nome terminará em "0" no exemplo abaixo.)
    
     ![Ferramenta de provisionamento do usuário mostrando a guia de criação do usuário.](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a>Botão Criar Usuários

Quando você clica no botão **Criar Usuários,** os parâmetros de entrada inseridos são validados. Se houver erros de validação, você será solicitado a corrigi-los. Ou, se todos os valores estão corretos, os usuários começarão a aparecer no AD (em qualquer UO especificada). Você verá uma barra de progresso na parte inferior da ferramenta enquanto ela é executado. Não feche o aplicativo enquanto a barra de progresso estiver ativa.
  
A criação do usuário leva tempo, portanto, planeje-se de acordo. Esse processo pode levar de vários minutos para alguns usuários até algumas horas para um grande número de usuários.
  
Se você não tiver acesso ao Controlador de Domínio do AD em seu ambiente de teste, ainda poderá validar a criação do usuário fazendo logom como um dos usuários no intervalo de usuários que você especificou para criar. Lembre-se de usar o prefixo e o sufixo, juntamente com o @sipDomain nome de usuário. Veja um exemplo:  <em>TestUser20@contoso.net</em>  .
  
> [!NOTE]
> Se os usuários já existirem, clicar no botão Criar Usuários os atualizará com quaisquer alterações de configuração. 
  
#### <a name="delete-users-button"></a>Botão Excluir Usuários

Quando você clicar no botão **Excluir Usuários,** os parâmetros de entrada da guia serão validados. Se houver erros de validação, você será solicitado a corrigi-los e, se os valores de entrada estão corretos, os usuários de teste especificados serão desabilitados e excluídos do Active Directory. Novamente, uma barra de progresso aparecerá na parte inferior dessa guia, e você não deverá fechar o aplicativo enquanto a barra de progresso estiver ativa.
  
> [!NOTE]
> Somente números de telefone formatados nos EUA são suportados. Os números de telefone são sempre atribuídos aos usuários, e todos os usuários criados pelo UserProvisioningTool.exe são habilitados para o Enterprise Voice por padrão. Qualquer cenário que use o número de telefone, como o Atendente Automático de Conferência ou chamadas UC-PSTN, use esse número de telefone para rotear corretamente as chamadas. Por esse motivo, *cada usuário deve* ter um número de telefone *exclusivo.*
  
> [!NOTE]
> **Se você tiver que criar usuários duas vezes, o comando falhará, a menos que você use um código de área diferente ou se os usuários anteriores foram desabilitados usando o cmdlet Disable-CsUser usuário.**
  
> [!IMPORTANT]
> Antes de criar contatos, primeiro você precisa concluir a replicação do usuário (o que é feito na guia Usuários). 
  
> [!IMPORTANT]
> Se você acabou de criar seus usuários, precisará aguardar até que a replicação do Skype for Business Server seja concluída e preencha as contas de usuário no banco de dados. **Se os usuários não terminarem de replicar, você verá um erro.** Você saberá quando os usuários terão terminado de replicar se o serviço front-end do Skype for Business Server 2015 tiver sido iniciado ou executando com êxito o cmdlet Get-CsUser no último usuário do número total especificado.
  
#### <a name="contacts-creation-tab"></a>Guia Criação de Contatos

Essa guia permite que você dê detalhes dos contatos dos usuários para seu teste.
  
![Ferramenta de provisionamento do usuário mostrando a guia Criação de Conteúdo.](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a>Para configurar os contatos dos usuários, faça o seguinte:

1. No campo **Média de Contatos por** Usuário, insira o número médio de contatos a ser preenchido nas listas de contatos de cada usuário.
    
2. Marque a **caixa de** seleção Fixa se quiser criar um número igual de contatos para cada usuário. Se você quiser variar o número de contatos criados para os usuários, des marque essa caixa de seleção.
    
3. No campo **Média de Grupos de Contatos por** Usuário, insira o número de grupos de contatos por usuário. Esse número precisa ser menor que a **Média de Contatos por Usuário.**
    
4. No campo **Porcentagem de Contatos federados/entre pools,** dê um número entre 0 e 100. Essa porcentagem de contatos será criada com os usuários federados.
    
5. No campo **Prefixo de Usuário Federado/Entre Pools,** dê o nome de usuário para usuários federados que serão adicionados às listas de contatos de usuários locais.
    
6. No campo Domínio SIP do Usuário **Federado/Entre Pools,** dê o Nome de Domínio SIP dos usuários federados.
    
7. Na **guia Criação do** Usuário, certifique-se de que as informações estão corretas. Seus contatos serão criados a partir de valores na guia Criação de Usuário.
    
8. Clique **em Criar Contatos para** iniciar a criação do contato. Esse processo pode levar vários minutos. Após a conclusão, uma caixa de diálogo será exibida com a mensagem "Operação Concluída com Êxito". Você pode validar os contatos que foram criados fazendo logom como um usuário que foi criado a partir da guia Criação de Usuário.
    
    > [!NOTE]
    > Depois que os contatos são criados, essa ferramenta reiniciará todos os Servidores front-end no pool de destino. Pode levar mais (até 2 horas) para que os Servidores front-end iniciem, dependendo de quantos contatos foram criados por essa operação. 
  
#### <a name="distribution-list"></a>Lista de distribuição

A Ferramenta de Stress and Performance do Skype for Business Server 2015 pode simular o recurso de expansão da Lista de Distribuição (DL) no cliente Skype for Business 2015. Você pode ignorar esta etapa se não pretende habilitar a expansão de DL na ferramenta de Provisionamento de Usuário.
  
![Ferramenta de Provisionamento de Usuário mostrando a guia Criação de Lista de Distribuição.](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
A guia Lista de Distribuição permite que você crie DLs que a Ferramenta de Stress and Performance usará para o recurso de Expansão da Lista de Distribuição. Antes de criar DLs, o Skype for Business Server 2015 precisa ser implantado, incluindo ter executado ForestPrep. Se isso não for feito, os atributos DL não existirão no esquema do AD, portanto, a ferramenta não poderá criar DLs.
  
### <a name="to-configure-distribution-lists"></a>Para configurar listas de distribuição:

1. No campo **Número** de Listas de Distribuição, dê o número total de DLs que você deseja criar (a recomendação aqui é que você comece com um valor que seja o dobro do número de usuários que você tem.).
    
2. In the **Distribution List Prefix field,** enter a prefix that all the DLs you create will have, for example *testDL*  . Isso significa que, em 100 DLs, seus nomes DL terão a aparência: testDL0, testDL1, até testDL99.
    
3. In the **Minimum Members in a Dist. List** field, enter the minimum number of users to put in each DL.
    
4. In the **Maximum Members in a Dist. List** field, enter the maximum number of users to add in each DL.
    
#### <a name="create-distribution-lists-button"></a>Botão Criar Listas de Distribuição

Quando você clica no botão Criar Listas de Distribuição, a ferramenta consulta o Active Directory para ver se as listas de distribuição que coincidem com o prefixo e os números já existem. A ferramenta cria todas as DLs que ainda não existem. Ao adicionar membros a essas Listas de Distribuição recém-criadas, ele escolherá os usuários no intervalo especificado na guia Criação do Usuário.
  
#### <a name="location-info-service-config-tab"></a>Guia Configuração do Serviço de Informações de Local

A Ferramenta de Stress and Performance do Skype for Business Server 2015 também pode gerar arquivos de configuração fictícios para o Serviço de Informações de Local. Observe que o Serviço de Informações de Local normalmente não tem impacto significativo no desempenho dos servidores. 
  
![Ferramenta de provisionamento do usuário mostrando a guia Configuração do Serviço de Informações de Local.](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
Se você optar por testar esse recurso, preencha os valores no formulário e clique no botão Gerar arquivos de configuração LIS, que criará. Arquivos CSV chamados:
  
- LIS_Subnet.csv
    
- LIS_Switches.csv
    
- LIS_Ports.csv
    
- LIS_WAP.csv
    
Para importar esses arquivos para o banco de dados LIS, use estes cmdlets do PowerShell:
  
- Set-CsLisSubnet
    
- Set-CsLisSwitch
    
- Set-CsLisPort
    
- Set-CsWirelessAccessPoint
    
## <a name="configure-user-profile"></a>Configurar Perfil de Usuário
<a name="BKMK_UserProfile"> </a>

Depois que seus usuários são criados (por meio da Ferramenta de Criação de Usuário), você pode configurar perfis de usuário com a ferramenta configuração de carga (UserProfileGenerator.exe) do Skype for Business Server 2015.
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a>Executando a ferramenta Configuração de Carga do Skype for Business Server 2015

Inicie a ferramenta Configuração de Carga (UserProfileGenerator.exe) e preencha as guias. Essa ferramenta cria um diretório para cada um dos computadores cliente que você precisará para executar suas simulações. Cada diretório de cliente vem com um script para iniciar a ferramenta de Stress and Performance (LyncPerfTool.exe) do Skype for Business Server 2015. As seções abaixo darão exemplos de como preencher os campos em cada guia da ferramenta Configuração de Carga do Skype for Business Server 2015.
  
> [!IMPORTANT]
> Os valores específicos do usuário usados na ferramenta de Configuração de Carga (UserProfileGenerator.exe) devem corresponder aos valores especificados na Ferramenta de Criação de Usuário (UserProvisioningTool.exe) do Skype for Business Server 2015 para o pool. 
  
#### <a name="common-configuration-tab"></a>Guia Configuração Comum

A **guia Configuração** Comum da Ferramenta de Configuração de Carga é mostrada abaixo. Preencha os campos da guia Configuração Comum, conforme descrito nas etapas a seguir.
  
![A guia Provisionamento do Usuário mostrando a guia Configuração Comum.](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. No campo **Número de Computadores** Disponíveis, digite o número de computadores que você deseja usar para executar a ferramenta Stress and Performance (LyncPerfTool.exe). Recomendamos que você tenha um computador para cada 4500 usuários que você simula, mas esse número pode variar se você reduzir o nível de carga ou usar apenas um subconjunto dos recursos disponíveis da ferramenta (os níveis de carga são definidos na guia Cenários Gerais).
    
2. No campo **Prefixo para Nomes de** Usuário, insira um prefixo para o campo nome de usuário de todos os usuários. Para fazer logoff no URI (Uniform Resource Identifier) será: *UserPrefix[User Start Index... (Número de usuários-1)] @User Domain*  , por exemplo, myUser009@Contoso.com.
    
3. No campo **Senha para Todos os Usuários,** insira a senha usada durante a criação dos usuários. Se você deixar esse campo vazio, o nome de usuário será definido como a senha.
    
4. No campo **Índice de Início do** Usuário, insira o índice do primeiro usuário a ser configurado. Você pode configurar intervalos diferentes para diferentes tipos ou níveis de carga, mas deve executar a ferramenta configuração de carga (UserProfileGenerator.exe) uma vez por intervalo que deseja configurar.
    
5. No campo **Número de Usuários,** insira o número total de usuários que você vai configurar.
    
6. No campo **Domínio do** Usuário, insira o domínio usado para o URI do SIP. Isso é usado para construir o URI sip de cada usuário para fazer logoff no Servidor de Front End do Skype for Business Server 2015 ou servidor Standard Edition e pode ser diferente do Domínio da Conta.
    
7. No campo **Domínio da** Conta, insira o logon do domínio do AD DS.
    
8. No campo **Porcentagem MPOP** (Porcentagem de Vários Pontos de Presença), dê um valor para a porcentagem de usuários que estão conectados de vários dispositivos ou máquinas, por exemplo, 10%.
    
9. Insira o número máximo de pontos de extremidade simultâneos no campo **Entrar por Segundo (por Instância).** Esse é o número máximo de logins para seus usuários, e a recomendação é uma taxa menor que/igual a 2 por segundo (<=2).
    
10. No campo Proxy de Acesso ou **FQDN** do Pool, insira o FQDN (nome de domínio totalmente qualificado) do servidor ao qual você deseja que os clientes se conectem. Se os usuários estão fazendo logom externamente, você precisará digitar o proxy de acesso. Se os usuários são internos, dê o FQDN de seu pool Enterprise ou servidor Standard Edition.
    
11. No campo **Porta,** insira a porta que você deseja que os usuários usem para SIP (o padrão aqui é 5061).
    
12. Para o **campo Configurações do Servidor de** Rede Externa, dê o FQDN do Proxy de Acesso ou pool e, novamente, a **porta**. Essas configurações são usadas apenas para simulação de carga de pontos de extremidade externos.
    
#### <a name="general-scenarios-tab"></a>Guia Cenários Gerais

![Ferramenta de Configuração de Carregamento mostrando a guia Cenários Gerais.](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
Você pode configurar os níveis de carga e os parâmetros para cada um dos cenários gerais oferecidos determinando o que você deseja executar ou deixar desabilitado. Aqui estão suas opções gerais:
  
> [!NOTE]
> Valores de nível de carga para todos os campos, mas os Serviços de Informações Locais estão **Desabilitados** **,** Baixo , **Médio** **,** Alto ou **Personalizado.** Se você selecionar qualquer configuração, mas desabilitada, as configurações serão geradas para cada cliente. Alto resultado na carga máxima suportada no servidor; médio é 60% de alta carga; o valor baixo é 30%. 
  
- **Sistema de Mensagens Instantâneas -** Isso inclui conferência e ponto a ponto; escolha o valor apropriado para o Nível de Carga.
    
- **Audioconferência -** Escolha um nível de carga somente para *audioconferência.* As chamadas ponto a ponto serão abordadas um pouco mais tarde na seção **Cenários de** Voz. Abra a **guia Avançado** para habilitar MultiView.
    
- **Compartilhamento de Aplicativos -** Escolha um nível de carga para compartilhamento de aplicativos.
    
- **Colaboração de Dados -** Escolha um nível de carga para colaboração de dados, que inclui conferência de dados.
    
- **Expansão da Lista de Distribuição -** Clique no **botão** Avançado e preencha o campo com os mesmos valores configurados na guia DL da Ferramenta de Criação de Usuário (UserProvisioningTool.exe). Escolha um nível de carga.
    
- **Consulta à Web do Livro de Endereços -** Este é o serviço de procurar do livro de endereços em vez do download do arquivo do livro de endereços. Se você quiser habilitar isso para downloads de arquivo do livro de endereços, clique no botão Avançado e de definir **EnableABSDownload** como True.  Dê um valor para o nível de carga.
    
- **Serviço de Grupo de Resposta -** Clique no **botão Avançado** e especifique os URIs dos grupos de resposta que você já criou quando provisionou agentes do Serviço de Grupo de Resposta. Você deve escolher pelo menos um grupo de resposta. Para usar mais, separe os grupos de resposta com ponto e vírgula. Atualize **RGSUriSuffixStartIndex** e **RGSUriSuffixEndIndex** para os valores reais. Escolha um nível de carga.
    
- **Serviços de Informações de Local -** Selecione um nível de carga habilitado ou desabilitado.
    
> [!NOTE]
> Cada um dos cenários tem um botão Avançado localizado ao lado dele e um conjunto de caixas de seleção que permitem variações para a configuração padrão. 
  
- Escolher  *Ad-hoc permitirá*  que a ferramenta gere simulação de conferências que serão criadas durante a hora.
    
- Escolher  *Grande Conf*  significa que um cenário de conferência grande será simulado.
    
-  *Externo*  informa a ferramenta para simular também usuários externos.
    
Esses botões e caixas de seleção são valores extras específicos para cada cenário e alterarão o comportamento da Ferramenta de Stress and Performance e tornarão a personalização possível.
  
Para cada cenário na guia Cenários Gerais (exceto para Os Serviços de Informações de Local), se o valor do Nível de Carga for **Personalizado,** a taxa de conversa será calculada usando o campo correspondente na caixa de diálogo Avançado. O nome do campo pode diferir, dependendo do cenário, mas a descrição do campo irá dizer: OBSERVAÇÃO Este número só será usado se Personalizado for selecionado no *menu suspenso.*
  
Os valores **Alto**, **Médio** e Baixo **alterarão** as taxas de conversa por modalidade de acordo com o Modelo de Usuário que é um equilíbrio de todos os cenários. Se houver a necessidade de alterar o nível de carga por modalidade devido a uma diferença no uso esperado, use uma taxa de conversa personalizada.
  
#### <a name="voice-scenarios-tab"></a>Guia Cenários de Voz

Essa é a guia para configuração de todos os cenários relacionados à voz.
  
![Guia Cenários de Voz da ferramenta Configuração de Carregamento.](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
Suas opções são:
  
- **VoIP -** Clique no **botão Avançado** e adicione valores para os campos PhoneAreaCode e LocationProfile (plano de discagem). Você também dará um valor para o Nível de Carga. Se você escolher um nível de carga para VoIP ou Gateway UC/PSTN habilitado, um arquivo de configuração de rede telefônica pública comutado (PSTN) para UC (comunicações unificadas) será gerado para simular chamadas externas.
    
- **Gateway UC/PSTN -** Você precisa escolher um valor de Nível de Carga e, quando escolher algo diferente de Desabilitado, também terá que fornecer um valor para o código de área PSTN clicando no **botão** Avançado. Clique **em Adicionar** sob o Servidor de Mediação e PSTN. Certifique-se de que você tenha uma rota configurada para o código de área.
    
    > [!TIP]
    > Você pode usar o Painel de Controle do Skype for Business ou o Shell de Gerenciamento do Skype for Business para verificar a configuração da rota de voz. 
  
- **Atendente de Conferência -** Fornecer um valor para o Nível de Carga. Qualquer valor diferente de Desabilitado habilita o **campo Número de** Telefone. Insira o número de telefone do Atendente Automático que você deseja usar. Clique **em Avançado** e dê um valor para o campo **LocationProfile.**
    
- **Serviço de Estacionamento de Chamada -** Aqui, fornece um nível de carga.
    
- **Servidor de Mediação e PSTN -** Cada Servidor de Mediação que você deseja usar precisa de seu próprio simulador PSTN. Depois de determinar qual cliente você usará para o simulador, configure o Servidor de Mediação para rotear chamadas para esse computador no Simulador PSTN que você configurou. Clique no **botão Adicionar** para configurar um valor para o Servidor de Mediação.
    
    > [!NOTE]
    > Cada cenário tem um botão Avançado localizado ao lado dele. As caixas de diálogo avançadas contêm configurações específicas para cada cenário que alteram o comportamento da Ferramenta de Stress and Performance e permitem a personalização. > For each scenario on the Voice Scenarios tab, if the value of Load Level is **Custom**, then the conversation rate will be calculated by using the corresponding field in the Advanced dialog box. O nome do campo pode diferir, dependendo do cenário, mas a descrição do campo irá dizer: OBSERVAÇÃO Este número só será usado se Personalizado for selecionado no *menu suspenso.*
  
#### <a name="web-app-tab"></a>Guia Aplicativo Web

![Ferramenta Configuração de Carregamento, guia Aplicativo Web.](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
O Web App dá suporte a cenários de conferência por meio do servidor UCWA (Unified Communications Web API) instalado em um servidor front-end. Use a guia Aplicativo Web para configurar todos os cenários relacionados ao aplicativo Web. As opções são:
  
- **Configurações Gerais do Aplicativo Web -** Clique no **botão Configurações** Adicionais e defina **ReachTargetServerUrl** como o VIP (IP virtual) do Pool de Diretórios do VIP do pool de Front-End.
    
- **Compartilhamento de Aplicativos -** Selecione um valor para o Nível de Carga.
    
- **Colaboração de Dados -** Selecione um valor para o Nível de Carga.
    
- **Sistema de Mensagens Instantâneas -** Selecione um valor para o Nível de Carga.
    
- **Conferência de voz -** Selecione um valor para o Nível de Carga.
    
> [!NOTE]
> Cada um dos cenários tem **um botão** Avançado localizado ao lado dele. As caixas de diálogo avançadas contêm valores específicos para cada cenário que alterarão o comportamento da Ferramenta de Stress and Performance e permitirão a personalização.> Para cada um dos cenários do Aplicativo Web, se o Nível de Carga for **Personalizado,** o valor especificado no campo **ConversationsPerHour** será usado em vez do padrão.
  
#### <a name="mobility-tab"></a>Guia Mobilidade

Use esta guia para configurar todos os cenários relacionados à mobilidade.
  
![Guia Mobilidade da ferramenta Configuração de Carregamento.](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
As opções aqui são:
  
- **Configurações gerais de mobilidade -** Clique **em Configurações Adicionais** e defina o campo UcwaTargetServerUrl como o VIP (IP virtual) do Pool de Diretores ou o VIP do pool de Front-End.
    
- **Presença e mensagens instantâneas/áudio P2P -** Selecione um valor para o Nível de Carga para habilitar a simulação de mobilidade.
    
> [!NOTE]
> Cada um dos cenários tem **um botão** Avançado localizado ao lado dele. As caixas de diálogo avançadas contêm valores específicos para cada cenário que alterarão o comportamento da Ferramenta de Stress and Performance e permitirão a personalização.> Para cada um dos cenários de Mobilidade, se o Nível de Carga for **Personalizado,** o valor especificado no campo **ConversationsPerHour** será usado em vez do padrão.
  
#### <a name="summary-tab"></a>Guia Resumo

A guia Resumo indica quais usuários usar para cada um dos cenários.
  
![Guia Resumo da ferramenta Configuração de Carregamento.](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
A guia Resumo indica quais usuários usar para cada um dos cenários. 
  
É possível configurar manualmente intervalos de números  de usuário, selecionando a caixa de seleção Habilitar Geração de Intervalo de Usuários Personalizado e clicando duas vezes no cenário na tabela que tem o Intervalo de Usuários que você deseja personalizar.
  
Verificar **(RunClient.bat)** Adicione atraso de login ao iniciar para incluir atrasos nos arquivos em lotes gerados para corresponder à taxa de login. Isso é útil para evitar a sobrecarga do servidor ao entrar em um grande número de usuários.
  
Clique **em Gerar** Arquivos e selecione a pasta onde você deseja gerar a configuração. Uma caixa de diálogo será exibida quando seus arquivos foram criados com êxito.
  
![A caixa de mensagem "Carregar arquivos de configuração gerados com êxito". Basta clicar em OK.](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a>Executar LyncPerfTool
<a name="BKMK_RunTool"> </a>

Você precisará criar usuários, contatos e cenários antes de executar a Ferramenta de Stress and Performance do Skype for Business Server 2015 (LyncPerfTool.exe). Para obter detalhes sobre como usar as ferramentas para executar essas ações, consulte [Create Users and Contacts](using-the-tool.md#BKMK_CreateUsersAndContacts) and [Configure User Profile](using-the-tool.md#BKMK_UserProfile) previously in this article. Executar essas ferramentas também gerará um arquivo que será executado com a ferramenta Stress and Performance como parte de um arquivo em lotes com os parâmetros necessários incluídos.
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Executando a ferramenta de Stress and Performance do Skype for Business Server 2015

A ferramenta Configuração de Carga (UserProfileGenerator.exe) cria um arquivo em lotes que permite executar a ferramenta de Stress and Performance (LyncPerfTool.exe) registrando contadores de desempenho e carregando o arquivo de configuração XML. O arquivo em lotes executa uma instância de LyncPerfTool.exe por arquivo de configuração. Para executar o arquivo em lotes, siga estas etapas:
  
### <a name="run-the-stress-and-performance-test"></a>Executar o teste de estresse e desempenho

1. Copie a pasta com as pastas de configuração e os arquivos dentro para o diretório que LyncPerfTool.exe em cada computador cliente. (Por exemplo, se você gerou os arquivos de configuração na pasta chamada 1.28_13.16.16, copie essa pasta para a pasta LyncPerfTool.exe-la. Faça isso em cada cliente.)
    
2. Navegue até a pasta do cliente e execute o script em lotes **RunClient.** Você pode clicar duas vezes no arquivo em lotes no Windows Explorer e ele executará todos os arquivos de configuração para esse cliente. Você também pode executar o script de uma pasta do cliente usando a seguinte sintaxe:
    
   ```console
   RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
   ```

Para executar a ferramenta Stress and Performance diretamente, abra um prompt de comando e digite o seguinte comando na linha de comando (e ao fazer isso pela primeira vez, registre os contadores de desempenho, conforme mostrado na observação posteriormente neste  `regsvr32 /i /n /s LyncPerfToolPerf.dll` tópico):
  
```console
LyncPerfTool.exe /file:IM_client0.xml
```

Para que a ferramenta exibir os valores no arquivo de configuração, inclua o parâmetro no comando anterior, para que  `/displayfile` ele tenha esta aparência:
  
```console
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

Para  *finalizar*  o processo, pressione Ctrl+C.
  
> [!NOTE]
> Antes de executar a ferramenta Stress and Performance diretamente, você deve registrar os contadores de desempenho por meio do seguinte comando:  `regsvr32 /i /n /s LyncPerfToolPerf.dll`
  
> [!NOTE]
> Todas as instâncias da ferramenta de Stress and Performance que você iniciar começarão a entrar imediatamente nos usuários, geralmente a uma taxa de um usuário por segundo. 
  
A taxa de pico de login do usuário para o pool é de cerca de 12 por segundo. Isso significa que você não deve iniciar mais de 12 instâncias de LyncPerfTool.exe ao mesmo tempo enquanto os usuários ainda estão se inndo. Mil usuários levarão cerca de 20 minutos para entrar totalmente em um por segundo.
  
## <a name="interpreting-the-results"></a>Interpretar os resultados
<a name="BKMK_Interpret"> </a>

A Ferramenta de Stress and Performance do Skype for Business Server 2015 tem muitos contadores que podem ajudá-lo a entender o que o cliente está fazendo e se está encontrando problemas.
  
### <a name="client-counters"></a>Contadores de cliente

Cada instância do LyncPerfTool.exe em execução tem uma instância separada dos contadores. Cada instância é nomeada por sua ID de processo. Se os clientes estão sobrecarregados, outros problemas podem ocorrer. Para evitar esses problemas:
  
- Monitore o uso da CPU e da memória nos computadores cliente. Se a CPU estiver consistentemente acima de 90%, reduza o número de usuários.
    
- Quando o espaço na memória é alto, você pode ter problemas se o arquivo de página começar a ficar sem espaço. Verifique se a Cobrança de Confirmação não está atingindo o limite no computador. Se você estiver executando limites de memória, considere aumentar o tamanho do arquivo de página ou reduzir o número de usuários.
    
Aqui está uma lista dos principais contadores de desempenho:
  
**Informações Gerais**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Tempo gasto em minutos  <br/> |Tempo gasto desde o início do processo.  <br/> |
|Pontos de extremidade ativos  <br/> |Número de pontos de extremidade atualmente conectados ao servidor.  <br/> |
|Logons com falha  <br/> |Número total de falhas de login do ponto de extremidade.  <br/> |
|Tentativas de logon  <br/> |Número total de tentativas de login do ponto de extremidade.  <br/> |
|Pontos de extremidade desconectados  <br/> |Número total de pontos de extremidade que foram desconectados.  <br/> |
   
**Informações de presença**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Chamadas SetPresence  <br/> |Número total de tentativas de alteração de presença. Para diferentes tipos de alterações de presença, consulte SetPresence (Presence Type) Calls Performance Counter.  <br/> |
|Respostas NNN para SetPresence  <br/> |Número total de códigos de resposta nnn recebidos do servidor.  <br/> |
|Chamadas getPresence  <br/> |Número total de tentativas de solicitação de presença.  <br/> |
|Respostas NNN para GetPresence  <br/> |Número total de códigos de resposta nnn recebidos do servidor.  <br/> |
   
**Informações do serviço de Agenda**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Tentativa de downloads de arquivos completos/delta do ABS  <br/> |Número total de tentativas de download de arquivos completos ou delta.  <br/> |
|Downloads de arquivos completos/delta do ABS bem-sucedidos  <br/> |Número total de tentativas de download de arquivos completos ou delta.  <br/> |
|Contadores relacionados ao serviço de Consulta à Web do Address Book  <br/> |Contadores relacionados ao download do arquivo do livro de endereços.  <br/> |
|Tentativa de chamadas do ABS WS  <br/> |Número total de tentativas de solicitações do serviço de Consulta à Web do Address Book.  <br/> |
|Chamadas WS abs bem-sucedidas  <br/> |Número total de solicitações do serviço de Consulta à Web do Address Book que retornaram um código de resposta bem-sucedido.  <br/> |
|Falhas nas chamadas do ABS WS  <br/> |Número total de solicitações do serviço de Consulta à Web do Address Book que retornaram um código de resposta de erro.  <br/> |
   
> [!NOTE]
> Essa categoria inclui contadores usados para monitorar downloads de arquivos do Serviço de Address Book (ABS) e solicitações de serviço de Consulta à Web do Address Book. 
  
**Informações da Lista de Distribuição (DL)**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Chamadas tentada  <br/> |Número total de tentativas de solicitações de serviço Web de expansão de lista de distribuição (DLX).  <br/> |
|Chamadas bem-sucedidas  <br/> |Número total de solicitações de serviço Web DLX que retornaram um código de resposta bem-sucedido.  <br/> |
|Falhas nas chamadas  <br/> |Número total de solicitações de serviço Web DLX que retornaram um código de resposta de erro.  <br/> |
   

  
> [!NOTE]
> Os contadores de desempenho listados abaixo reportam os números de todas as chamadas VoIP, incluindo chamadas para o Servidor de Mediação, Servidor de Conferência A/V, Servidor de Borda, aplicativo Grupo de Resposta e Atendente Automático de Conferência, quando esses cenários estão habilitados. 
  
**Informações básicas de VoIP**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Chamadas ativas  <br/> |Número total de chamadas de voz de entrada/saída em andamento no momento.  <br/> |
|Chamadas Encerradas  <br/> |Número total de chamadas de voz de entrada/saída já encerradas.  <br/> |
|Chamadas recusadas  <br/> |Número total de chamadas de voz de entrada recusadas.  <br/> |
|Tentativas de chamadas de entrada/saída  <br/> |Número total de tentativas de chamadas de voz de entrada/saída.  <br/> |
|Chamadas de entrada/saída estabelecidas  <br/> |Número total de chamadas de voz de entrada/saída estabelecidas.  <br/> |
|Chamadas NNN recebidas  <br/> |Número total de códigos de resposta nnn recebidos do servidor.  <br/> |
|Taxa de aprovação voIP (%)  <br/> |Total de chamadas estabelecidas/Total de chamadas tentadas.  <br/> |
   
**Informações de Chamada do Serviço de Grupo de Resposta**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Chamadas ativas  <br/> |Número total de chamadas ativas para o aplicativo Grupo de Resposta.  <br/> |
|Chamadas tentada  <br/> |Número total de chamadas tentada.  <br/> |
   
**Informações de chamada de mensagens instantâneas (IM)**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Chamadas ativas  <br/> |Número total de chamadas contínuas de mensagens instantâneas de entrada/saída.  <br/> |
|Chamadas Encerradas  <br/> |Número total de chamadas de mensagens instantâneas de entrada/saída já encerradas.  <br/> |
|Chamadas NNN recebidas  <br/> |Número total de códigos de resposta nnn recebidos do servidor.  <br/> |
|Mensagens de IM recebidas/enviadas  <br/> |Número total de mensagens recebidas ou enviadas para todas as sessões.  <br/> |
|Tentativas de chamadas de entrada/saída  <br/> |Número total de tentativas de chamadas de mensagens instantâneas de entrada/saída.  <br/> |
|Chamadas de entrada/saída estabelecidas  <br/> |Número total de chamadas de mensagem instantânea de entrada/saída estabelecidas.  <br/> |
   
**Informações de chamada de compartilhamento de aplicativos**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Chamadas ativas  <br/> |Número total de chamadas contínuas de compartilhamento de aplicativos de entrada/saída.  <br/> |
|Chamadas Encerradas  <br/> |Número total de chamadas de compartilhamento de aplicativos de entrada/saída já encerradas.  <br/> |
|Chamadas NNN recebidas  <br/> |Número total de códigos de resposta nnn recebidos do servidor.  <br/> |
|Tentativas de chamadas de entrada/saída  <br/> |Número total de tentativas de chamadas de compartilhamento de aplicativos de entrada/saída.  <br/> |
|Chamadas de entrada/saída estabelecidas  <br/> |Número total de chamadas de compartilhamento de aplicativos de entrada/saída estabelecidas.  <br/> |
   
**Informações de chamada caa**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Chamadas ativas  <br/> |Número total de chamadas PSTN (rede telefônica pública comutado) de entrada/saída em andamento no momento.  <br/> |
|Chamadas Encerradas  <br/> |Número total de chamadas PSTN de entrada/saída já encerradas.  <br/> |
|Tentativas de chamadas de entrada/saída  <br/> |Número total de tentativas de chamadas PSTN de entrada/saída.  <br/> |
|Chamadas de entrada/saída estabelecidas  <br/> |Número total de chamadas PSTN de entrada/saída estabelecidas.  <br/> |
   
**Informações de conferência**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Conferências ativas de mensagens instantâneas  <br/> |Número total de conferências contínuas de mensagens instantâneas.  <br/> |
|Conferências de áudio/vídeo ativas  <br/> |Número total de conferências contínuas de áudio/vídeo (A/V).  <br/> |
|Conferências de compartilhamento de aplicativos ativas  <br/> |Número total de conferências contínuas de compartilhamento de aplicativos.  <br/> |
|Número de participantes  <br/> |Número total de participantes conectados a conferências no momento.  <br/> |
|Falha no Agendamento de Conferências  <br/> |Número total de falhas ao tentar agendar uma conferência.  <br/> |
|Falha na conferência de ingressar  <br/> |Número total de falhas ao tentar se conectar a uma conferência.  <br/> |
   
**Contadores de cliente UCWA**

|**Contador de desempenho**|**Descrição**|
|:-----|:-----|
|Número total de junções IMMCU bem-sucedidas  <br/> |Número total de conferências de mensagens instantâneas ingressadas.  <br/> |
|Número total de junções de DMCU bem-sucedidas  <br/> |Número total de conferências A/V ingressados.  <br/> |
   

