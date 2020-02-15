---
title: Definir e configurar um pool de front-ends ou servidor Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a Front End pool or Standard Edition server
ms:assetid: 713fc263-23dd-414a-b001-82932e4fe966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398538(v=OCS.15)
ms:contentKeyID: 48184457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f35c49ab232bd69184191ab841431e6c80eca20a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036471"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a>Definir e configurar um pool Front-end ou um servidor Standard Edition no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-08_

Este procedimento não exige associação a um grupo de administradores locais ou de domínio privilegiado. Você deve fazer logon em um computador como usuário padrão.

Se você estiver implantando um servidor corporativo, um número mínimo de servidores front-end em um pool deve estar sempre em execução. A tabela a seguir resume esses requisitos.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Número total de servidores front-end em um pool</th>
<th>Número de servidores que devem estar em execução para o pool ser funcional</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1-2</p></td>
<td><p>1 </p></td>
</tr>
<tr class="even">
<td><p>3-4</p></td>
<td><p>2 </p></td>
</tr>
<tr class="odd">
<td><p>5-6</p></td>
<td><p>3 </p></td>
</tr>
<tr class="even">
<td><p>7-8</p></td>
<td><p>4 </p></td>
</tr>
<tr class="odd">
<td><p>9-10</p></td>
<td><p>5 </p></td>
</tr>
<tr class="even">
<td><p>11-12</p></td>
<td><p>6 </p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> Para o Lync Server 2013, sempre que você adicionar ou remover um servidor front-end do pool, você deve reiniciar os serviços. A remoção e adição de servidores devem ser feitas como operações separadas. Por exemplo, se você for adicionar dois servidores front-end e remover dois servidores front-end, use o seguinte processo: 
> <OL>
> <LI>
> <P>Remova os dois servidores front-end.</P>
> <LI>
> <P>Publique e reative a topologia.</P>
> <LI>
> <P>Reinicie os serviços</P>
> <LI>
> <P>Adicione os dois servidores front-end.</P>
> <LI>
> <P>Publique e reative a topologia.</P>
> <LI>
> <P>Reinicie os serviços.</P></LI></OL>



</div>

Após ter definido sua topologia, use o procedimento a seguir para definir um pool de front-ends para o site. Para obter detalhes sobre como definir a topologia, consulte [definir e configurar uma topologia no construtor de topologias para o Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).

<div>

## <a name="to-define-a-front-end-pool"></a>Para definir um pool de front-ends

1.  No Assistente para Definir Novo Pool de Front-Ends, na página **Defina um Novo Pool de Front-Ends**, clique em **Avançar**.

2.  Na página **definir o FQDN do pool de front-ends** , digite um FQDN (nome de domínio totalmente qualificado) para o pool que você está criando, clique em **pool de front-ends Enterprise Edition**e, em seguida, clique em **Avançar**.

3.  Na página **definir os computadores neste pool** , digite um FQDN de computador para o primeiro servidor front-end no pool e clique em **Adicionar**. Repita essa etapa para todos os computadores adicionais (até doze) que você deseja adicionar ao pool e clique em **Avançar**.

4.  Na página **Selecionar recursos**, marque as caixas de seleção para os recursos que você deseja neste pool de Front-Ends. Por exemplo, se você estiver implantando apenas recursos de mensagens instantâneas (IM) e presença, marque a caixa de seleção **conferência** para permitir mensagens instantâneas com vários participantes, mas não selecionaria as caixas de seleção **conferência de discagem (PSTN)**, **Enterprise Voice**ou **controle de admissão de chamada** , pois representam recursos de voz, vídeo e conferência colaborativa.
    
      - **Conferência**   esta seleção habilita um rico conjunto de recursos, incluindo:
        
          - IM com mais de duas partes em uma sessão de mensagens instantâneas
        
          - Conferência, que inclui a colaboração de documento, o compartilhamento de aplicativo e o compartilhamento de área de trabalho.
        
          - Conferência a/V, que permite que os usuários tenham conferências de áudio/vídeo (A/V) em tempo real sem a necessidade de serviços externos, como o serviço Live Meeting ou uma ponte de áudio de terceiros.
    
      - **A conferência**   discada (PSTN) permite que os usuários ingressem na parte de áudio de uma conferência do Lync Server 2013 usando um telefone PSTN (rede telefônica pública comutada) sem exigir um provedor de audioconferência.
    
      - **O Enterprise Voice**   Enterprise Voice é a solução de voz sobre IP (VoIP) no Lync Server 2013 que permite que os usuários façam e recebam chamadas telefônicas. Você implantaria esse recurso se planeja usar o Lync Server 2013 para chamadas de voz, caixa postal e outras funções que usam um dispositivo de hardware ou um cliente de software.
    
      - **O CAC (controle de admissão de chamadas)**   determina, com base na largura de banda de rede disponível, se deve permitir sessões de comunicação em tempo real, como chamadas de voz ou vídeo a serem estabelecidas. Se você implantou apenas IM e presença, o CAC não é necessário porque nenhum destes dois recursos usam o CAC.
    
      - **Archiving Archiving**oferece uma maneira de arquivar conteúdo de IM, de conferência (reunião) ou ambos enviados por meio do Lync Server 2013.   
    
      - **Monitoring**   Monitoring Server permite coletar dados numéricos que descrevem a qualidade de mídia em sua rede e pontos de extremidade, informações de uso relacionadas a chamadas de VoIP, mensagens de IM, conversas A/V, reuniões, compartilhamento de aplicativos e transferências de arquivos e informações de erro de chamada e de solução de problemas para chamadas com falha.
    
    <div>
    

    > [!NOTE]
    > Se você deseja habilitar o CAC na implantação, é necessário habilitar o CAC em exatamente um pool por site central. O CAC é recomendado se você está implantando os recursos de voz ou conferência de A/V.

    
    </div>
    
    A tabela a seguir mostra os recursos disponíveis (superior) e as funções oferecidas aos usuários (esquerdo). As seleções na tabela são aquelas que você deve selecionar para habilitar estes recursos para sua organização.
    
    
    <table>
    <colgroup>
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th></th>
    <th>Conferências</th>
    <th>Conferência discada</th>
    <th>Enterprise Voice</th>
    <th>Serviço de Controle de Admissão de Chamadas</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Sistema de mensagens instantâneas e presença</p></td>
    <td><p>X</p></td>
    <td></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="even">
    <td><p>Conferências</p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="odd">
    <td><p>Conferências A/V</p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    <td></td>
    <td><p>X</p></td>
    </tr>
    <tr class="even">
    <td><p>Enterprise Voice</p></td>
    <td></td>
    <td></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    </tr>
    </tbody>
    </table>


5.  Na página **selecionar funções de servidor posicionadas** , você pode colocar o servidor de mediação no servidor front-end ou implantá-lo como um servidor autônomo.
    
    Você pode colocar o servidor de mediação no pool de front-ends.
    
      - Se você pretende colocar o servidor de mediação no pool de front-ends Enterprise Edition, verifique se a caixa de seleção está marcada. As funções de servidor serão implantadas nos servidores do pool.
    
      - Se você pretende implantar o servidor de mediação como um servidor autônomo, desmarque a caixa de seleção apropriada. Você implantará o servidor de mediação em uma etapa de implantação separada após a implantação completa do servidor front-end.
    
    <div>
    

    > [!NOTE]
    > Recomendamos colocar o servidor de mediação, se possível. Para obter detalhes sobre o suporte a servidores de mediação posicionados ou autônomos, consulte <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Components and topologias for Mediation Server in Lync server 2013</A> na documentação de planejamento.

    
    </div>

6.  A página **associar funções de servidor a este pool de front-ends** permite definir e associar funções de servidor ao pool de front-ends. A seguinte função está disponível:
    
    **Habilitar um pool**   de borda define e associa um único servidor de borda ou um pool de servidores de borda. Um servidor de borda facilita a comunicação e a colaboração entre usuários dentro da organização e pessoas de fora da organização, incluindo usuários federados.
    
    Existem dois cenários possíveis que você pode usar para implantar e associar as funções do servidor:
    
    Para o cenário um, você está definindo uma nova topologia para uma nova instalação. É possível abordar a instalação em uma das duas seguintes formas:
    
      - Desmarque a caixa de seleção e prossiga com a definição da topologia. Após publicar, configurar e testar as funções de servidor front-end e back-end, você poderá executar o construtor de topologias novamente para adicionar os servidores de função à topologia. Essa estratégia permitirá que você teste o pool de front-ends e o servidor que executa o SQL Server sem complicações adicionais de funções adicionais. Depois de concluir o teste inicial, você poderá executar o construtor de topologias novamente para selecionar as funções que precisa implantar.
    
      - Selecione as funções que você precisa instalar e configure o hardware para acomodar as funções selecionadas.
    
    Para o cenário dois, você tem uma implantação existente e sua infraestrutura está pronta para novas funções ou você precisa associar as funções existentes a um novo servidor front-end:
    
      - Nesse caso, você selecionará as funções que pretende implantar ou associar ao novo servidor front-end. Em qualquer caso, você continuará com a definição das funções, configurar qualquer hardware necessário e continuar com a instalação.

7.  Na página **Definir o repositório SQL**, siga um destes procedimentos:
    
      - Para usar um repositório de SQL Server existente que já foi definido em sua topologia, selecione uma instância do **Repositório SQL**.
    
      - Para definir uma nova instância do SQL Server para armazenar informações de pool, clique em **novo** e ESPECIFIQUE o **FQDN do SQL Server**na caixa de diálogo **definir novo repositório SQL** .
    
      - Para especificar o nome de uma instância de SQL Server, selecione **Instância nomeada** e especifique o nome da instância.
    
      - Para usar a instância padrão, clique em **Instância padrão**.
    
      - Para usar o espelhamento SQL, selecione **Habilitar espelhamento do SQL** e selecione uma instância existente ou crie uma nova instância.

8.  Na página **Definir o compartilhamento de arquivo**, execute um dos seguintes procedimentos:
    
      - Para usar um compartilhamento de arquivo que já foi definido na sua topologia, selecione **Usar um compartilhamento de arquivos definido anteriormente**.
    
      - Para definir um novo compartilhamento de arquivo, selecione **Definir um novo compartilhamento de arquivo** na caixa **FQDN do Servidor de Arquivos**, insira o FQDN do servidor de arquivos existente onde o compartilhamento de arquivo deve residir e insira um nome para o compartilhamento de arquivo na caixa **Compartilhamento de Arquivos**.
    
    <div>
    

    > [!IMPORTANT]
    > O compartilhamento de arquivos do Lync Server 2013 não pode ser localizado no servidor front-end. Observe que neste exemplo, o compartilhamento de arquivo foi localizado no servidor Back-End com base no SQL Server. Este pode não ser um local ideal para as necessidades da sua organização, um servidor de arquivos pode ser uma escolha melhor. Você pode definir o compartilhamento de arquivos sem que este tenha sido criado. Será necessário criar o compartilhamento de arquivos no local que você definir antes de publicar a topologia.

    
    </div>

9.  Na página **Especificar a URL dos serviços Web**, execute um ou estes dois procedimentos:
    
    <div>
    

    > [!IMPORTANT]
    > A URL base é a identidade dos Serviços Web para a URL, menos o https://. Por exemplo, se a URL completa para os serviços Web do pool for https://pool01.contoso.net, a URL base será pool01.contoso.net.

    
    </div>
    
    <div>
    

    > [!WARNING]
    > Se você tiver mais de um pool de front-ends ou servidor front-end, o FQDN de serviços Web externos deverá ser exclusivo. Por exemplo, se você definir o FQDN de serviços Web externos de um servidor front-end como <STRONG>pool01.contoso.com</STRONG>, não será possível usar o <STRONG>pool01.contoso.com</STRONG> para outro pool de front-ends ou servidor front-end.

    
    </div>
    
    1.  Se você estiver configurando o balanceamento de carga DNS, marque a caixa de seleção **substituir o FQDN do pool de serviços Web interno** , digite a URL base interna (que deve ser diferente do FQDN do pool e\<pode ser,\>por exemplo, interna-a URL base) na **URL base interna**.
        
        <div>
        

        > [!WARNING]
        > Se você decidir substituir os serviços Web internos por um FQDN autodefinido, cada FQDN deverá ser exclusivo de qualquer outro pool de front-ends, diretor ou um pool de diretores. <STRONG>Use apenas caracteres padrão</STRONG> (incluindo a – z, A – z, 0 – 9 e hifens) ao definir URLs ou nomes de domínio totalmente qualificados. Não use caracteres Unicode ou sublinhados. Não há suporte para caracteres não padrão em uma URL ou FQDN em CAs externas e CAs públicas (ou seja, quando a URL ou FQDN deve ser atribuído ao nome da entidade ou ao nome alternativo da entidade no certificado).

        
        </div>
    
    2.  Opcionalmente, insira a URL base externa em **URL base externa**. Insira a URL base externa para diferenciá-la da nomeação de domínio interna. Por exemplo, seu domínio interno é contoso.net, mas seu nome de domínio externo é contoso.com. Você deve definir a URL usando o nome do domínio contoso.com. Isso também é importante no caso de um proxy reverso. O nome de domínio da URL base externa seria igual ao nome de domíniodo  FQDN do proxy inverso. Mensagens instantâneas e presença exigem acesso HTTP ao pool de front-ends.
    
    <div>
    

    > [!NOTE]
    > Para usar o balanceamento de carga DNS, você deve criar os registros DNS apropriados. Para obter detalhes, consulte <A href="lync-server-2013-configure-dns-for-load-balancing.md">Configurar o DNS para balanceamento de carga no Lync Server 2013</A>.

    
    </div>

10. Se você selecionou **conferência** na página **selecionar recursos** , na página **selecionar um servidor do Office Web Apps** , selecione **associar pool com um servidor do Office Web Apps** e clique em **novo** (ou selecione um servidor do Office Web Apps existente na lista suspensa).

11. Na caixa de diálogo **Definir Novo Servidor Office Web Apps**, digite o FQDN (nome de domínio totalmente qualificado) do computador do Servidor Office Web Apps na caixa **FQDN do Servidor Office Web Apps**. Quando você fizer isso, a URL de descoberta de seu Servidor Office Web Apps deverá ser inserida automaticamente na caixa **Office Web URL de descoberta de Servidor Office Web Apps**.
    
    Se o servidor do Office Web Apps estiver instalado no local e na mesma zona de rede do Lync Server 2013, a opção **Office Web Apps Server é implantada em uma rede externa (ou seja, perímetro/Internet)** não deve ser selecionada.
    
    Se o Servidor Office Web Apps for implantado fora do seu firewall interno, seleciona a opção **O Servidor Office Web Apps é implantado em uma rede externa (ou seja, de perímetro/Internet)**.
    
    <div>
    

    > [!NOTE]
    > Para obter detalhes, consulte <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013</A>.

    
    </div>

12. Na página **Definir o Repositório do SQL de Arquivamento**, selecione uma instância existente do SQL Server ou defina uma nova instância para armazenar os dados associados a arquivamento.

13. Na página **Definir o Repositório do SQL de Monitoramento**, selecione uma instância existente do SQL Server ou defina uma nova instância para armazenar os dados associados a monitoramento.

14. Clique em **Avançar**. Se você definiu outros servidores de função na página **associar funções de servidor a este pool de front-ends** , as páginas do assistente de configuração de função separada serão abertas para permitir que você configure as funções de servidor. Para obter detalhes, consulte:
    
    [Implantando o acesso de usuário externo no Lync Server 2013](lync-server-2013-deploying-external-user-access.md)

15. Se você não selecionou funções do servidor adicionais para configurar e implantar ou quando você finalizou a configuração dos servidores de função adicionais, clique em **Concluir**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

