---
title: Configurar perfil de usuário
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure User Profile
ms:assetid: 52713245-e502-4539-a238-66ff1aca26b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945594(v=OCS.15)
ms:contentKeyID: 51541419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 842a5ade3e0484d0b084f48ac75a2b13984706e5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-user-profile"></a>Configurar perfil de usuário

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2018-10-11_

As ferramentas incluídas no pacote de ferramentas de desempenho e stress do Lync Server 2013 permitem que você crie e configure as contas de usuário de teste que você pode usar para executar simulações de carga. Use a ferramenta de criação de usuário do Lync Server 2013 para criar os usuários. (Para obter detalhes, consulte [Create Users and contacts](create-users-and-contacts.md).) Depois que os usuários são criados, configure os perfis de usuário usando a ferramenta de configuração de carregamento do Lync Server 2013.

<div>

## <a name="running-the-lync-server-2013-load-configuration-tool"></a>Executando a ferramenta de configuração de carregamento do Lync Server 2013

Para configurar perfis de usuário, execute a ferramenta de configuração de carregamento do Lync Server 2013 (UserProfileGenerator. exe) e preencha cada uma das guias. O UserProfileGenerator. exe gera um diretório para cada computador cliente que você precisa para executar a simulação. Cada diretório de cliente também vem com um script para iniciar todas as instâncias da ferramenta de estresse e desempenho do Lync Server 2013 (LyncPerfTool. exe).

<div>


> [!IMPORTANT]  
> Os valores específicos do usuário especificados em UserProfileGenerator devem corresponder aos valores especificados na ferramenta de criação de usuário (UserProvisioningTool) do Lync Server 2013 para o pool.



</div>

Preencha os campos em cada guia da ferramenta de configuração de carga do Lync Server 2013, conforme descrito nas seções a seguir.

<div>

## <a name="common-configuration"></a>Configuração comum

A guia **configuração comum** da ferramenta de configuração de carregamento do Lync Server 2013 é mostrada na figura a seguir. Preencha os campos da guia **configuração comum** , conforme descrito nas etapas a seguir.

![Guia configuração comum.](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Guia configuração comum.")

1.  Em **número de máquinas disponíveis**, digite ou clique no número de computadores que você deseja usar para executar o LyncPerfTool. exe. Recomendamos que você tenha um computador para todos os usuários do 4.500 que você vai simular. Esse número pode variar se você reduzir o nível de carga ou se usar apenas um subconjunto dos recursos disponíveis. (Os níveis de carga são definidos na guia **cenários gerais** .)

2.  Em **prefixo para nomes de usuário**, digite o prefixo para o nome de usuário dos usuários. Para fazer logon, o URI (Uniform Resource Identifier) será: userprefix\[User Start index... (Número de usuários-1) \]@User domínio.

3.  Em **senha para todos os usuários**, insira a senha usada para a criação dos usuários. Se você deixar este campo vazio, o nome de usuário será usado como a senha.

4.  Em **Iniciar índice de usuário**, clique ou digite o índice do primeiro usuário a ser configurado. Você pode configurar intervalos diferentes para diferentes tipos ou níveis de carga, mas deve executar o UserProfileGenerator. exe uma vez pelo intervalo que você deseja configurar.

5.  Em **número de usuários**, clique ou digite o número total de usuários que você vai configurar.

6.  Em **domínio do usuário**, digite o domínio usado para o URI do SIP. Isso é usado para construir o URI SIP de cada usuário para fazer logon no servidor front-end do Lync Server 2013 ou no servidor Standard Edition. Pode ser diferente do domínio da conta.

7.  Em **domínio da conta**, digite o logon do domínio dos serviços de domínio do Active Directory.

8.  Insira o número máximo de pontos de extremidade simultâneos em **entrar por segundo (por instância)** para o qual você deseja que a ferramenta faça logon em todos os pontos de extremidade/usuários. A taxa recomendada é \<= 2 por segundo/SKU padrão Fe.

9.  Em **proxy de acesso ou FQDN de pool**, digite o nome de domínio totalmente qualificado (FQDN) do servidor ao qual você deseja que os clientes se conectem. Se os usuários estiverem fazendo logon externamente, especifique o proxy de acesso. Se os usuários forem internos, especifique o FQDN do seu pool ou servidor Standard Edition.

10. Em **porta**, clique ou digite a porta que você deseja que os usuários usem para SIP (o padrão é 5061).

Para configurações de servidor de rede externo, especifique o **proxy de acesso ou o FQDN do pool** e a **porta**. Essas configurações são usadas apenas para simulação de carga de pontos de extremidade externos.

</div>

<div>

## <a name="general-scenarios"></a>Cenários gerais

A guia **cenários gerais** da ferramenta de configuração de carregamento do Lync Server 2013 é mostrada na figura a seguir.

Configure os níveis de carga e os parâmetros para cada um dos cenários gerais que você deseja executar ou deixe desabilitado.

![Guia cenários gerais.](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "Guia cenários gerais.")

1.  Em **mensagens instantâneas**, que incluem ponto-a-ponto e conferência, especifique o valor apropriado para o nível de carga.
    
    <div>
    

    > [!NOTE]  
    > Os valores de nível de carga para todos os campos (exceto serviços de informações de local) são <STRONG>desabilitados</STRONG>, <STRONG>baixo</STRONG>, <STRONG>médio</STRONG>, <STRONG>alto</STRONG>e <STRONG>personalizado</STRONG>. Quando baixo, médio, alto ou personalizado for selecionado, as configurações serão geradas para cada cliente e modalidade. Alto fará com que a carga de máximo com suporte seja gerada para o servidor, média corresponde a 60% da carga e baixa corresponde a 30% da carga.

    
    </div>

2.  Na **audioconferência**, que é apenas a audioconferência, especifique o valor apropriado para o nível de carga. As chamadas ponto a ponto são abordadas na seção cenários de voz mais adiante neste tópico. Para habilitar o MultiView, abra a guia **avançado** para essa modalidade.

3.  Em **compartilhamento de aplicativos**, especifique o valor apropriado para o nível de carga.

4.  Em **colaboração de dados**, que inclui a conferência de dados, especifique o valor apropriado para o nível de carga.

5.  Em **expansão de lista de distribuição**, especifique o valor apropriado para o nível de carga. Você também deve clicar no botão **avançado** e, em seguida, preencher os campos com os mesmos valores que você configurou na guia **lista de distribuição** da ferramenta de criação de usuário do Lync Server (UserProvisioningTool. exe). Para obter detalhes sobre esses campos, consulte [Create Users and contacts](create-users-and-contacts.md)

6.  Na **consulta à Web do catálogo de endereços**, que é o serviço de pesquisa de catálogo de endereços (não o download do arquivo do catálogo de endereços), especifique o valor apropriado para o nível de carga. Para habilitar downloads do catálogo de endereços, clique no botão **avançado** correspondente e, em seguida, defina **EnableABSDownload** como true.

7.  Em **serviço de grupo de resposta**, especifique o valor apropriado para o nível de carga. Você também deve clicar no botão **avançado** correspondente e especificar os URIs dos grupos de resposta que você já criou ao provisionar os agentes de serviço do grupo de resposta. É necessário especificar pelo menos um grupo de resposta. Use pontos-e-vírgulas para separar vários grupos de resposta. Atualize o RGSUriSuffixStartIndex e o RGSUriSuffixEndIndex para os valores reais.

8.  Em **serviços de informações de local**, selecione o valor apropriado para o nível de carga. O nível de carga para o local Information Services deve ser **habilitado** ou **desabilitado**.

<div>


> [!NOTE]  
> Cada um dos cenários tem um botão <STRONG>avançado</STRONG> localizado ao lado dele e um conjunto de caixas de seleção que permitem variações dos cenários. O <STRONG>ad-hoc</STRONG> significa gerar simulação de conferências que serão criadas durante a hora. <STRONG>Grande conf</STRONG> significa que o cenário de conferência grande será simulado. <STRONG>External</STRONG> significa também simular usuários externos.<BR>Esses botões e caixas de seleção permitem acesso a valores específicos para cada cenário que alterará o comportamento da ferramenta de estresse e desempenho do Lync Server 2013 (LyncPerfTool) e tornará a personalização possível. Para cada cenário na guia <STRONG>cenários gerais</STRONG> (exceto para serviços de informações de local), se o valor de nível de carga for <STRONG>personalizado</STRONG>, a taxa de conversa será calculada usando o campo correspondente na caixa de diálogo <STRONG>avançado</STRONG> . O nome do campo difere, dependendo do cenário, mas a descrição do campo entrará em estado, "Observação: este número só será usado se personalizado for selecionado no menu suspenso." Em geral, os valores <STRONG>alto</STRONG>, <STRONG>médio</STRONG>e <STRONG>baixo</STRONG> mudarão as taxas de conversa por modalidade em linha com o modelo de usuário que é um saldo de todos os cenários. Se houver necessidade de alterar o nível de carga por modalidade devido à diferença de uso esperado, recomendamos usar uma taxa de conversa <STRONG>personalizada</STRONG> .<BR>



</div>

</div>

<div>

## <a name="voice-scenarios"></a>Cenários de voz

A guia **cenários de voz** da ferramenta de configuração de carregamento do Lync Server 2013 é mostrada na figura a seguir.

Use a guia **cenários de voz** para configurar todos os cenários relacionados à voz.

![Guia cenários de voz.](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Guia cenários de voz.")

1.  Em **VoIP**, clique no botão **avançado** e forneça valores para os campos **PhoneAreaCode** e **LocationProfile** (plano de discagem). Você também deve especificar um valor para o **nível de carga**. Se o nível de carga para **VoIP** e o **Gateway de UC/PSTN** estiver habilitado, será sempre gerado um arquivo de configuração de rede telefônica pública comutada (PSTN) para comunicação unificada (UC) que irá simular chamadas externas.

2.  No **Gateway UC/PSTN**, especifique um valor para o nível de carga. Se você selecionar um nível de carga diferente de **desabilitado**, deverá fornecer um valor para o **código de área PSTN** clicando no botão **Adicionar** em servidor de mediação e PSTN. Verifique se você tem uma rota configurada para esse código de área.
    
    <div>
    

    > [!NOTE]  
    > Você pode usar o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server para verificar a configuração da rota de voz.

    
    </div>

3.  Em **atendedor de conferência**, especifique um valor para o nível de carga. Selecionar um nível de carga (diferente de **desabilitado**) habilitará o campo **número de telefone** . Insira o número de telefone do atendedor automático que você deseja usar. Além disso, clique no botão **avançado** e, em seguida, especifique um valor para o campo **LocationProfile** .

4.  Em **serviço de estacionamento de chamada**, especifique o valor apropriado para o **nível de carga**.

5.  No **servidor de mediação e PSTN**, para cada servidor de mediação que você deseja usar, você deve ter um simulador PSTN separado. Depois de determinar qual cliente será usado como o simulador, você precisará configurar seu servidor de mediação para rotear chamadas para esse computador na porta de simulador PSTN que você configurou. Clique em **Adicionar** para configurar o valor do servidor de mediação.

<div>


> [!NOTE]  
> Cada um dos cenários tem um botão <STRONG>avançado</STRONG> localizado ao lado dele. Esses botões permitem o acesso a valores específicos para cada cenário que alterará o comportamento da ferramenta de estresse e desempenho do Lync Server 2013 (LyncPerfTool) e habilitará a personalização. Para cada cenário na guia <STRONG>cenários de voz</STRONG> , se o valor de <STRONG>nível de carga</STRONG> for <STRONG>personalizado</STRONG>, a taxa de conversa será calculada usando o campo correspondente na caixa de diálogo <STRONG>avançado</STRONG> . O nome do campo difere, dependendo do cenário, mas a descrição do campo entrará em estado, "Observação: este número só será usado se personalizado for selecionado no menu suspenso."



</div>

</div>

<div>

## <a name="reach"></a>Contactar

Reach é uma nova experiência no Lync Server 2013 que oferece suporte a cenários de conferência por meio do servidor UCWA (Unified Communications Web API) instalado no servidor front-end. A guia **REACH** da ferramenta de configuração de carregamento do Lync Server 2013 é mostrada na figura a seguir.

Use a guia **alcance** para configurar todos os cenários relacionados ao alcance.

![Guia alcance.](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Guia alcance.")

1.  Clique no botão **avançado** ao lado de **configurações de REACH gerais**. Defina o campo **UcwaTargetServerUrl** como o VIP (IP virtual) do pool diretor ou o VIP do pool de front-ends.

2.  Em **compartilhamento de aplicativos**, **colaboração de dados**e **im**, selecione o valor apropriado para o **nível de carga**.

<div>


> [!NOTE]  
> Cada um dos cenários tem um botão <STRONG>avançado</STRONG> localizado ao lado dele. Esses botões permitem o acesso a valores específicos para cada cenário que alterará o comportamento da ferramenta de estresse e desempenho do Lync Server 2013 (LyncPerfTool) e habilitará a personalização. Para cada um dos cenários de alcance, se o <STRONG>nível de carga</STRONG> for <STRONG>personalizado</STRONG>, o valor especificado no campo <STRONG>ConversationsPerHour</STRONG> será usado em vez do padrão



</div>

Use a guia **mobilidade** para configurar todos os cenários relacionados à mobilidade.

![Guia Mobility.](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Guia Mobility.")

1.  Clique no botão **avançado** ao lado de **mobilidade (UCWA)**. Defina o campo **UcwaTargetServerUrl** como o VIP (IP virtual) do pool diretor ou o VIP do pool de front-ends.

2.  Em **presença e áudio de mensagens\\instantâneas P2P**, selecione o valor apropriado para o **nível de carga** para habilitar a simulação de cenário de mobilidade.

<div>


> [!NOTE]  
> Cada um dos cenários tem um botão <STRONG>avançado</STRONG> localizado ao lado dele. Esses botões permitem o acesso a valores específicos para cada cenário que alterará o comportamento da ferramenta de estresse e desempenho do Lync Server 2013 (LyncPerfTool) e habilitará a personalização. Para cada um dos cenários de alcance, se o <STRONG>nível de carga</STRONG> for <STRONG>personalizado</STRONG>, o valor especificado no campo <STRONG>ConversationsPerHour</STRONG> será usado em vez do padrão.



</div>

</div>

<div>

## <a name="summary"></a>Resumo

A guia **Resumo** da ferramenta de configuração de carregamento do Lync Server 2013 é mostrada na figura a seguir.

![Guia Resumo.](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Guia Resumo.")

A guia **Resumo** indica quais usuários usar para cada um dos cenários. É possível configurar manualmente intervalos de números de usuário, marcando a caixa de seleção **habilitar geração de intervalo de usuários personalizados** e clicando duas vezes no cenário na tabela que tem o **intervalo de usuários** que você deseja personalizar. Check (RunClient. bat) adicionar atraso de entrada ao iniciar, a fim de incluir atrasos nos arquivos de lote gerados para corresponder à taxa de entrada. Isso é útil para evitar a sobrecarga do servidor ao entrar em um grande número de usuários. Clique em **gerar arquivos**e selecione a pasta onde você deseja gerar a configuração. Uma caixa de diálogo semelhante à figura a seguir será exibida quando os arquivos forem criados com êxito.

![Reconhecimento de que os arquivos foram criados.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Reconhecimento de que os arquivos foram criados.")

</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Criar usuários e contatos](create-users-and-contacts.md)  
</div>
</div>
<span></span>
</div>
</div>
</div>
