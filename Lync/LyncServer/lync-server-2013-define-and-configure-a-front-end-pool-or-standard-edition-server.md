---
title: Definir e configurar um pool Front-End ou um servidor Standard Edition
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
ms.openlocfilehash: ddc430370c59e279e0e36aa662da0f33973e0d80
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a>Definir e configurar um pool Front-End ou um servidor Standard Edition no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-03-08_

Esse procedimento não requer associação em um administrador local ou em um grupo de domínio privilegiado. Você deve fazer logon em um computador como usuário padrão.

Se você estiver implantando um servidor corporativo, um número mínimo de servidores front-end em um pool deve estar sempre em execução. A tabela a seguir resume esses requisitos.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Número total de servidores front-end no pool</th>
<th>Número de servidores que devem estar em execução para o pool ser funcional</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1-2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3-4</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>5-6</p></td>
<td><p>3</p></td>
</tr>
<tr class="even">
<td><p>7-8</p></td>
<td><p>4</p></td>
</tr>
<tr class="odd">
<td><p>9-10</p></td>
<td><p>5</p></td>
</tr>
<tr class="even">
<td><p>11-12</p></td>
<td><p>6</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> Para o Lync Server 2013, a qualquer momento em que você adicionar ou remover um servidor front-end do pool, você deve reiniciar os serviços. Remover e adicionar servidores deve ser feito como operações separadas. Por exemplo, se você vai adicionar dois servidores front-end e remover dois servidores front-end, use o seguinte processo: 
> <OL>
> <LI>
> <P>Remova os dois servidores front-end.</P>
> <LI>
> <P>Publique e ative novamente a topologia.</P>
> <LI>
> <P>Reiniciar os serviços</P>
> <LI>
> <P>Adicione os dois servidores front-end.</P>
> <LI>
> <P>Publique e ative novamente a topologia.</P>
> <LI>
> <P>Reinicie os serviços.</P></LI></OL>



</div>

Depois de definir sua topologia, use o procedimento a seguir para definir um pool de front-ends para seu site. Para obter detalhes sobre como definir a topologia, consulte [definir e configurar uma topologia no construtor de topologias para o Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).

<div>

## <a name="to-define-a-front-end-pool"></a>Para definir um pool de front-ends

1.  No assistente definir novo pool de front-end, na página **definir o novo pool de front-ends** , clique em **Avançar**.

2.  Na página **definir o FQDN do pool de front-end** , insira um nome de domínio totalmente qualificado (FQDN) para o pool que você está criando, clique em **pool de front-end Enterprise Edition**e clique em **Avançar**.

3.  Na página **definir os computadores neste pool** , insira um FQDN do computador para o primeiro servidor front-end do pool e clique em **Adicionar**. Repita essa etapa para qualquer computador adicional (até doze) que você deseja adicionar ao pool e clique em **Avançar**.

4.  Na página **selecionar recursos** , marque as caixas de seleção dos recursos que você deseja neste pool de front-ends. Por exemplo, se você estiver implantando apenas mensagens instantâneas e recursos de presença, marque a caixa de seleção **conferência** para permitir mensagens instantâneas com vários participantes, mas não marque as caixas de seleção **conferência de discagem (PSTN)**, **Enterprise Voice**ou **controle de admissão de chamadas** , pois representam recursos de voz, vídeo e conferência colaborativa.
    
      - **Conferência**   essa seleção permite um conjunto avançado de recursos, incluindo:
        
          - Mensagens instantâneas com mais de duas partes em uma sessão de mensagens instantâneas.
        
          - Conferência, que inclui colaboração de documentos, compartilhamento de aplicativos e compartilhamento de área de trabalho.
        
          - Conferência a/V, que permite que os usuários tenham conferências de áudio/vídeo (A/V) em tempo real sem a necessidade de serviços externos, como o serviço Live Meeting ou uma ponte de áudio de terceiros.
    
      - **A conferência**   discada (PSTN) permite que os usuários ingressem na parte de áudio de uma conferência do Lync Server 2013 usando um telefone PSTN (rede telefônica pública comutada) sem precisar de um provedor de audioconferência.
    
      - **O Enterprise Voice**   Enterprise Voice é a solução de voz sobre IP (VoIP) no Lync Server 2013, que permite aos usuários fazer e receber chamadas telefônicas. Você pode implantar esse recurso se planeja usar o Lync Server 2013 para chamadas de voz, caixa postal e outras funções que usam um dispositivo de hardware ou um cliente de software.
    
      - **O controle de admissão de chamadas (CAC)**   o CAC determina, com base na largura de banda de rede disponível, se permite que sessões de comunicação em tempo real, como chamadas de voz ou com vídeo, sejam estabelecidas. Se você implantou apenas mensagens instantâneas e presença, o CAC não é necessário porque nenhum desses dois recursos usa o CAC.
    
      - **O arquivamento**de arquivamento fornece uma maneira de arquivar conteúdo de mensagens de chat, conteúdo de conferência (reunião) ou ambos enviados pelo Lync Server 2013.   
    
      - **Monitorando**   o monitoramento do servidor permite que você colete dados numéricos que descrevem a qualidade da mídia em sua rede e pontos de extremidade, informações de uso relacionadas a chamadas de VoIP, mensagens de chat, conversas de A/V, reuniões, compartilhamento de aplicativos e transferências de arquivos, além de informações de erro e de solução de problemas para chamadas com falha.
    
    <div>
    

    > [!NOTE]
    > Se você quiser habilitar o CAC em sua implantação, será necessário habilitar o CAC em exatamente um pool por site central. O CAC será recomendado se você estiver implantando recursos de voz ou conferência A/V.

    
    </div>
    
    A tabela a seguir mostra os recursos disponíveis (superior) e as funções oferecidas aos usuários (à esquerda). As seleções na tabela são o que você deve selecionar para habilitar esses recursos para a sua organização.
    
    
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
    <th>Conferência</th>
    <th>Conferência discada</th>
    <th>Enterprise Voice</th>
    <th>Serviço de Controle de Admissão de Chamadas</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Mensagens instantâneas e presença</p></td>
    <td><p>X</p></td>
    <td></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="even">
    <td><p>Conferência</p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="odd">
    <td><p>Conferências de áudio/vídeo</p></td>
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


5.  Na página **selecionar funções de servidor posicionadas** , você pode posicionar o servidor de mediação no servidor front-end ou implantá-lo como um servidor autônomo.
    
    Você pode posicionar o servidor de mediação no pool de front-ends.
    
      - Se você pretende posicionar o servidor de mediação no pool de front-end do Enterprise Edition, certifique-se de que a caixa de seleção esteja marcada. A função de servidor será implantada nos servidores do pool.
    
      - Se você pretende implantar o servidor de mediação como um servidor autônomo, desmarque a caixa de seleção apropriada. Você vai implantar o servidor de mediação em uma etapa de implantação separada após a implantação completa do servidor front-end.
    
    <div>
    

    > [!NOTE]
    > Recomendamos que você se colocação do servidor de mediação, se possível. Para obter detalhes sobre o suporte a servidores de mediação posicionados ou autônomos, consulte <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">componentes e topologias do servidor de mediação no Lync server 2013</A> na documentação de planejamento.

    
    </div>

6.  A página **associar funções de servidor a esta página de pool de front-end** permite definir e associar funções de servidor ao pool de front-end. A seguinte função está disponível:
    
    **Habilitar um pool**   de bordas define e associa um servidor de borda único ou um pool de servidores de borda. O servidor de borda intermedia a comunicação e colaboração entre os usuários dentro da organização e as pessoas de fora da organização, inclusive usuários federados.
    
    Há dois cenários possíveis que você pode usar para implantar e associar as funções de servidor:
    
    No cenário um, você está definindo uma nova topologia para uma nova instalação. Você pode abordar a instalação de uma destas duas maneiras:
    
      - Deixe a caixa de seleção desmarcada e prossiga com a definição da topologia. Após publicar, configurar e testar as funções de servidor front-end e back-end, execute o Construtor de Topologias novamente para adicionar os servidores de função à topologia. Essa estratégia permitirá testar o pool de front-ends e o servidor que executa o SQL Server sem complicações adicionais das funções adicionais. Depois de concluir o teste inicial, execute o Construtor de Topologias novamente para selecionar as funções necessárias para implantação.
    
      - Selecione as funções que você precisa instalar e configure o hardware para acomodar as funções selecionadas.
    
    Para o cenário dois, você tem uma implantação existente e sua infraestrutura está pronta para novas funções ou você precisa associar funções existentes a um novo servidor front-end:
    
      - Nesse caso, você selecionará as funções que pretende implantar ou associar ao novo servidor front-end. Em qualquer um dos casos, você continuará com a definição das funções, a configuração do hardware necessário e a instalação.

7.  Na página **definir a SQL Store** , siga um destes procedimentos:
    
      - Para usar um repositório de SQL Server existente que já foi definido em sua topologia, selecione uma instância do **Repositório SQL**.
    
      - Para definir uma nova instância do SQL Server para armazenar informações do pool, clique em **novo** e, em seguida, ESPECIFIQUE o **FQDN do SQL Server**na caixa de diálogo **definir novo repositório SQL** .
    
      - Para especificar o nome de uma instância de SQL Server, selecione **Instância Nomeada** e especifique o nome da instância.
    
      - Para usar a instância padrão, clique em **Instância padrão**.
    
      - Para usar o espelhamento do SQL, selecione **habilitar o espelhamento do SQL** e selecione uma instância existente ou crie uma nova instância.

8.  Na página **definir o compartilhamento de arquivos** , siga um destes procedimentos:
    
      - Para usar um compartilhamento de arquivo que já foi definido na sua topologia, selecione **Usar um compartilhamento de arquivos previamente definido**.
    
      - Para definir um novo compartilhamento de arquivo, selecione **Definir um novo compartilhamento de arquivo** na caixa **FQDN do Servidor de Arquivos**, insira o FQDN do servidor de arquivos existente onde o compartilhamento de arquivo deve residir e insira um nome para o compartilhamento de arquivo na caixa **Compartilhamento de Arquivos**.
    
    <div>
    

    > [!IMPORTANT]
    > O compartilhamento de arquivos do Lync Server 2013 não pode ser localizado no servidor front-end. Observe que, neste exemplo, o compartilhamento de arquivos foi localizado no servidor back-end baseado no SQL Server. Isso pode não ser um local ideal para os requisitos da sua organização, e um servidor de arquivos pode ser uma opção melhor. Você pode definir o compartilhamento de arquivos sem que ele tenha sido criado. Além disso, você precisará criar o compartilhamento de arquivos no local definido para poder publicar a topologia.

    
    </div>

9.  Na página **especificar a URL dos serviços Web** , siga um destes procedimentos ou ambos:
    
    <div>
    

    > [!IMPORTANT]
    > A URL base é a identidade dos serviços Web para a URL, menos "https://". Por exemplo, se a URL completa para os serviços Web do pool for https://pool01.contoso.net, a URL base será pool01.contoso.net.

    
    </div>
    
    <div>
    

    > [!WARNING]
    > Se você tiver mais de um pool de front-ends ou servidor front-end, o FQDN dos serviços Web externos deve ser exclusivo. Por exemplo, se você definir o FQDN de serviços Web externos de um servidor front-end como <STRONG>pool01.contoso.com</STRONG>, não será possível usar o <STRONG>pool01.contoso.com</STRONG> para outro pool de front-end ou servidor front-end.

    
    </div>
    
    1.  Se você estiver configurando o balanceamento de carga de DNS, marque a caixa de seleção **substituir FQDN do pool de serviços Web internos** , insira a URL base interna (que deve ser diferente da FQDN do pool e\<, por exemplo\>, interna-sua URL base) em **URL base interna**.
        
        <div>
        

        > [!WARNING]
        > Se você decidir substituir os serviços internos da Web por um FQDN autodefinido, cada FQDN deve ser exclusivo de qualquer outro pool de front-end, diretor ou um pool de diretor. <STRONG>Use apenas caracteres padrão</STRONG> (incluindo A–Z, a–z, 0–9 e hifens) ao definir URLs ou nomes de domínio totalmente qualificados. Não use caracteres Unicode ou sublinhados. Normalmente, caracteres não padrão no URL ou FQDN não são suportados por DNS externo e CAs públicas (ou seja, quando o URL ou FQDN deve ser atribuído ao nome da entidade ou ao nome alternativo da entidade no certificado).

        
        </div>
    
    2.  Opcionalmente, insira a URL base externa na **URL base externa**. Você digitaria a URL base externa para diferenciá-la de seu nome de domínio interno. Por exemplo, seu domínio interno é contoso.net, mas o seu nome de domínio externo é contoso.com. Você definiria a URL usando o nome de domínio contoso.com. Isso também é importante no caso de um proxy reverso. O nome de domínio da URL base externa seria igual ao nome de domínio do FQDN do proxy inverso. As mensagens instantâneas e a presença exigem acesso HTTP ao pool de front-ends.
    
    <div>
    

    > [!NOTE]
    > Para usar o balanceamento de carga de DNS, você deve criar os registros DNS apropriados. Para obter detalhes, consulte <A href="lync-server-2013-configure-dns-for-load-balancing.md">Configurar o DNS para balanceamento de carga no Lync Server 2013</A>.

    
    </div>

10. Se você selecionou **conferência** na página **selecionar recursos** , na página **selecionar um servidor do Office Web Apps** , selecione **associar pool com um servidor do Office Web Apps** e clique em **novo** (ou selecione um servidor existente do Office Web Apps na lista suspensa).

11. Na caixa de diálogo **Definir Novo Servidor do Office Web Apps**, digite o FQDN (nome de domínio totalmente qualificado) do computador do Servidor do Office Web Apps na caixa **FQDN do Servidor do Office Web Apps**. Quando você fizer isso, a URL de descoberta de seu Servidor do Office Web Apps deverá ser inserida automaticamente na caixa **Office Web URL de descoberta de Servidor do Office Web Apps**.
    
    Se o Office Web Apps Server estiver instalado no local e na mesma zona de rede do Lync Server 2013, a opção **Office Web Apps Server será implantada em uma rede externa (isto é, perímetro/Internet)** não deve ser selecionada.
    
    Se o Servidor do Office Web Apps for implantado fora do seu firewall interno, seleciona a opção **O Servidor do Office Web Apps é implantado em uma rede externa (ou seja, de perímetro/Internet)**.
    
    <div>
    

    > [!NOTE]
    > Para obter detalhes, consulte <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013</A>.

    
    </div>

12. Na página **definir a repositório do SQL Store** , selecione uma instância existente ou SQL Server, ou defina uma nova instância para armazenar os dados associados ao arquivamento de dados.

13. Na página **definir a loja do SQL Store** , selecione uma instância existente ou SQL Server, ou defina uma nova instância para armazenar os dados associados a dados de monitoramento.

14. Click **Next**. Se você definiu outros servidores de função na página **associar funções de servidor a esta página de pool de front-end** , as páginas do assistente de configuração de função separado serão abertas para permitir que você configure as funções do servidor. Para obter detalhes, consulte os seguintes artigos:
    
    [Implantação de acesso do usuário externo no Lync Server 2013](lync-server-2013-deploying-external-user-access.md)

15. Se você não selecionou funções de servidor adicionais para configurar e implantar, ou quando tiver terminado a configuração dos servidores de função adicionais, clique em **concluir**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

