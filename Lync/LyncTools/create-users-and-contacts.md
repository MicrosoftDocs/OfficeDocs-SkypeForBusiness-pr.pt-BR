---
title: Criar usuários e contatos
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Create Users and Contacts
ms:assetid: 04b24d07-2864-463d-b508-544c2674c4ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945587(v=OCS.15)
ms:contentKeyID: 51541412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f09ac6fd667b77b47e27ec9fb9caac44b9a13e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-users-and-contacts"></a>Criar usuários e contatos

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-22_

Você deve usar a ferramenta de provisionamento de usuário do Lync Server 2013 (UserProvisioningTool. exe) para criar usuários e contatos em preparação para testes de carga de desempenho e estresse.

Aqui está uma lista de termos e definições que podem ser úteis ao ler por meio deste tópico.

  - Unidade organizacional – unidade organizacional dos serviços de domínio Active Directory (OU).

  - Pool federado/cruzado – usuários que serão habilitados a se comunicar com usuários de outros serviços de mensagens instantâneas (IM), como MSN Network of Internet Services, AOL®\!e Yahoo®.

  - Listas de distribuição – os objetos nos serviços de domínio do Active Directory que contêm uma lista de usuários dos serviços de domínio Active Directory, usados para iniciar comunicações com grupos de pessoas.

  - Serviço de informações de localização – o serviço do Lync Server 2013 que, quando habilitado e configurado por telefone, permite a recuperação de localização física para os serviços do 9-1-1 (E9-1-1) aprimorados.

  - Números de telefone dos EUA – os números de telefone atribuídos aos usuários, além do URI SIP usado para roteamento de chamadas de entrada e saída e pesquisa de número reverso (RNL).

<div>

## <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Criar usuários e contatos usando o UserProvisioningTool. exe

Você deve usar a ferramenta de provisionamento de usuário do Lync Server para criar usuários e contatos para simulação de carga. A ferramenta de provisionamento de usuário do Lync Server é instalada com o pacote de ferramentas de desempenho e carga do Lync Server. Certifique-se de que o instalador de pacotes (CapacityPlanningTool. msi) foi executado no servidor front-end ou no servidor Standard Edition. Inicie a ferramenta de provisionamento de usuário do Lync Server executando o arquivo UserProvisioningTool. exe (localizado em% InstalledDirectory% LyncStressAndPerfTool\\LyncStress) no servidor front-end ou no servidor Standard Edition.

<div>


> [!IMPORTANT]  
> Você deve estar conectado como um membro do grupo de segurança Administradores de domínio para executar o UserProvisioningTool. exe. É necessário executar deste contexto porque UserProvisioningTool. exe estará criando e configurando novos usuários dos serviços de domínio Active Directory.



</div>

<div>


> [!NOTE]  
> Quando você cria um número significativo de usuários (10.000 ou mais), execute UserProvisioningTool. exe a partir de um computador high-end. Observe que o controlador de domínio também ocorrerá com alta carga enquanto os usuários estiverem sendo criados.



</div>

Quando a ferramenta de provisionamento de usuário do Lync Server abrir, clique em **configuração** e selecione **carregar configuração**. Para começar a configurar usuários e contatos, carregue o arquivo padrão que está incluído no pacote, SampleData. xml. Isso preencherá os campos com dados de exemplo que você precisará revisar para o seu sistema. Se você tiver um arquivo XML pré-configurado que já contém configurações personalizadas, carregue esse arquivo em vez disso. Preencha os campos da ferramenta de provisionamento de usuário do Lync Server, conforme descrito nas seções a seguir.

![Guia criação de usuários.] (images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "Guia criação de usuários.")

Para configurar as opções do servidor, siga estas etapas.

1.  No **FQDN do pool de front-end**, digite o nome de domínio totalmente qualificado (FQDN) do servidor Standard Edition ou do pool de front-end no qual você deseja hospedar os usuários.

2.  Em **prefixo do nome do usuário**, digite um prefixo que você deseja usar para criar nomes de usuário para fins de teste.

3.  Em **senha**, especifique uma senha que será aplicada a todas as contas de usuário de teste.

4.  Em **domínio SIP**, digite o nome do domínio a ser usado para testar os URIs SIP dos usuários (identificadores de recursos uniformes).

5.  Em **domínio da conta**, digite o nome do domínio do domínio atual dos serviços de domínio do Active Directory, no qual você deseja criar os usuários de teste.

6.  Em **unidade organizacional**, digite o nome da UO dos serviços de domínio Active Directory em que você deseja criar os objetos de usuário. Se a UO não existir, ela será criada.

7.  Em **código de área do telefone**, digite o código de área de três dígitos que será usado para testar contas de usuário. Certifique-se de que o código de área do telefone não entre em conflito com os códigos de área dos outros usuários nos serviços de domínio Active Directory.

8.  Marque a caixa de seleção habilitada para **voz** se quiser habilitar os usuários de teste para Enterprise Voice.

9.  Em **número de usuários**, especifique o número total de usuários de teste que você deseja criar.

10. Em **índice de início**, especifique o número inicial que será usado como sufixo para o prefixo do nome de usuário.

<div>

## <a name="create-users-button"></a>Botão criar usuários

Quando você clica no botão criar usuários, ele valida todos os parâmetros de entrada.

  - Se houver algum erro de validação, ele solicitará que você corrija os valores de entrada.

  - Se todos os valores de entrada estiverem corretos, ele começará a criar usuários nos serviços de domínio Active Directory. Uma barra de progresso será exibida na parte inferior deste formulário. Recomendamos que você não feche o aplicativo enquanto a barra de progresso estiver ativa.

A criação de usuários é um processo lento. Pode levar alguns minutos. Se o número de usuários for muito grande, o processo pode até levar algumas horas. Se os usuários já existirem, eles serão atualizados com qualquer alteração. Você pode validar que os usuários foram criados fazendo logon como um dos usuários no intervalo. Use o prefixo de usuário, número de usuário e @sipDomain como o nome de usuário (por exemplo, LyncUser10@contoso.net), juntamente com a senha especificada.

</div>

<div>

## <a name="delete-users-button"></a>Botão excluir usuários

Quando você clica no botão excluir usuários, ele valida todos os parâmetros de entrada.

  - Se houver algum erro de validação, ele solicitará que você corrija os valores de entrada.

  - Se todos os valores de entrada estiverem corretos, ele começará a desabilitar e excluir usuários nos serviços de domínio Active Directory. Uma barra de progresso será exibida na parte inferior deste formulário. Recomendamos que você não feche o aplicativo enquanto a barra de progresso estiver ativa.

<div>


> [!NOTE]  
> <OL>
> <LI>
> <P>Só há suporte para números de telefone formatados nos EUA. Os números de telefone são sempre atribuídos aos usuários, e todos os usuários criados pelo UserProvisioningTool. exe são habilitados para o Enterprise Voice. Qualquer cenário que use o número de telefone, como atendedor automático de conferência ou chamadas UC-PSTN, use esse número de telefone para direcionar as chamadas de forma adequada. Por esse motivo, cada usuário deve ter um número de telefone exclusivo. Se você precisar criar usuários duas vezes, o comando falhará, a menos que você use um código de área diferente, ou se os usuários anteriores foram desabilitados usando o cmdlet <STRONG>Disable-CsUser</STRONG> .</P>
> <LI>
> <P>Antes de criar contatos, você deve primeiro concluir a replicação do usuário, executada na guia usuários. Se você acabou de criar seus usuários, deve aguardar até que a replicação do Lync Server seja concluída e preencher as contas de usuário no banco de dados. Se os usuários ainda não concluírem a replicação, você verá um erro. Você saberá quando os usuários terminam de duplicar se o serviço de front-end do Lync Server 2013 foi iniciado ou executa com êxito o cmdlet <STRONG>Get-CsUser</STRONG> no último usuário.</P></LI></OL>



</div>

</div>

</div>

<div>

## <a name="contacts-creation-tab"></a>Guia criação de contatos

A guia criação de contatos permite que você especifique detalhes dos contatos dos usuários.

![Guia criação de contatos.] (images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Guia criação de contatos.")

Para configurar os contatos dos usuários, siga estas etapas.

1.  Em média de contatos por usuário, especifique o número médio de contatos a serem preenchidos nas listas de contatos para cada um dos usuários.

2.  Marque a caixa de seleção fixa se desejar criar um número igual de contatos para cada usuário. Se você quiser variar o número de contatos criados para os usuários, desmarque a caixa de seleção.

3.  Em média de grupos de contatos por usuário, especifique o número de grupos de contatos por usuário. Este número deve ser menor do que a média de contatos por usuário.

4.  Em porcentagem de contatos federados/entre pools, especifique um número entre 0 e 100. Esta porcentagem de contatos será criada com os usuários federados.

5.  Em prefixo de usuário federado/Cross pool, especifique o nome de usuário para os usuários federados que serão adicionados às listas de contatos de usuários locais.

6.  No domínio SIP do usuário de pool federado/cruzado, especifique o nome de domínio SIP dos usuários federados.
    
    <div>
    

    > [!NOTE]  
    > Nenhum dos usuários deve estar conectado ao criar contatos.

    
    </div>

7.  Na guia criação de usuário, verifique se os parâmetros estão corretos. O intervalo de usuários para o qual os contatos serão criados será obtido na guia criação de usuários.

8.  Clique em criar contatos para iniciar a criação do contato. Esse processo pode levar alguns minutos. Após a conclusão, será exibida uma caixa de diálogo com a mensagem "operação concluída com êxito". Você pode validar os contatos que foram criados fazendo logon como um usuário criado a partir da guia criação de usuários.
    
    <div>
    

    > [!NOTE]  
    > Após a criação dos contatos, essa ferramenta reiniciará todos os servidores de front-end no pool de destino. Pode demorar mais (até 2 horas) para que os servidores front-end sejam iniciados, dependendo de quantos contatos foram criados por essa operação.

    
    </div>

</div>

<div>

## <a name="distribution-list"></a>Lista de distribuição

Um dos recursos da ferramenta de sobrecarga e desempenho do Lync Server 2013 é simular o recurso de expansão da lista de distribuição (DL) no Lync 2013. Se você não for habilitar a expansão de DL no UserProvisioningTool, ignore esta etapa.

![Guia criação da lista de distribuição.] (images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Guia criação da lista de distribuição.")

A guia lista de distribuição permite que você crie DLs que a ferramenta de stress e desempenho usará para o recurso de expansão da lista de distribuição. Antes de criar DLs, o Lync Server 2013 já deve estar instalado. Você deve ter executado o Lync Server 2013 ForestPrep. Caso contrário, os atributos DL não existem no esquema dos serviços de domínio Active Directory e a ferramenta não será capaz de criar DLs.

Para configurar as listas de distribuição, siga estas etapas.

1.  Em número de listas de distribuição, especifique o número total de DLs que você deseja criar. (Recomendamos que você comece com o dobro do número de usuários). Elas são numeradas de 0 a n-1.

2.  Em prefixo da lista de distribuição, especifique o prefixo que a DLs terá. Por exemplo, se você especificar DLs 100 e um prefixo de testDL, a DLs será nomeada testDL0, testDL1 e assim por diante, por meio de testDL99.

3.  Em Membros mínimos em uma lista dist., especifique o número mínimo de usuários a serem adicionados em cada lista de distribuição.

4.  Em número máximo de membros em uma lista dist., especifique o número máximo de usuários a serem adicionados em cada lista de distribuição.

<div>

## <a name="create-distribution-lists-button"></a>Botão criar listas de distribuição

Quando você clica no botão criar listas de distribuição, a ferramenta consulta os serviços de domínio do Active Directory para ver se as listas de distribuição que correspondem ao prefixo e aos números já existem. A ferramenta irá criar apenas aqueles que ainda não existem. Ao adicionar membros a essas listas de distribuição recém-criadas, ele selecionará os usuários do intervalo especificado na guia criação de usuário.

</div>

</div>

<div>

## <a name="location-info-service-config-tab"></a>Guia Configuração do serviço de informações de localização

Um dos recursos da ferramenta de stress e desempenho do Lync Server 2013 é gerar arquivos de configuração fictícios para o serviço de informações de localização. O serviço de informações de localização geralmente não tem impacto significativo no desempenho dos servidores.

![Guia Configuração do serviço de informações de localização.] (images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Guia Configuração do serviço de informações de localização.")

Se optar por testar esse recurso, você poderá preencher os valores mencionados no formulário e clicar no botão gerar arquivos de configuração de LIS. Ele irá gerar arquivos CSV chamados LIS\_subnet. csv, Lis\_switches. csv,\_LIS Ports. csv e\_Lis. csv. Em seguida, você pode importar esses arquivos CSV para o banco de dados LIS usando o cmdlet **set-CsLisSubnet** , o cmdlet **set-CsLisSwitch** , o cmdlet **set-CsLisPort** e o cmdlet **set-CsWirelessAccessPoint** , respectivamente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

