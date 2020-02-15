---
title: 'Lync Server 2013: definir sua topologia de borda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define your edge topology
ms:assetid: 787b23f1-8fa0-4c37-abf2-c516c5dd66f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398591(v=OCS.15)
ms:contentKeyID: 48184562
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bd7c52eef58d4e40c767f48a296a83a8c056525
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-your-edge-topology-in-lync-server-2013"></a>Definir sua topologia de borda no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-28_

Você deve usar o construtor de topologias para criar sua topologia e deve configurar pelo menos um pool de front-ends interno ou servidor Standard Edition antes de poder implantar o servidor de borda. Use o procedimento a seguir para definir a topologia de borda de um servidor de borda único e, em seguida, use os procedimentos em [publicar sua topologia no Lync server 2013](lync-server-2013-publish-your-topology.md) e [exporte sua topologia do Lync Server 2013 e copie-o para a mídia externa para instalação de borda](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) para publicar a topologia e torná-la disponível para o servidor de borda.

<div>


> [!NOTE]  
> A interface de Borda interna e externa devem usar o mesmo tipo de balanceamento de carga. Não é possível usar o balanceamento de carga DNS na interface de Borda e o balanceamento de carga de hardware na outra interface de Borda.



</div>

Para publicar, habilitar ou desabilitar uma topologia com êxito ao adicionar ou remover uma função do servidor, você deve estar conectado a um usuário membro dos grupos RTCUniversalServerAdmins e de Administradores de Domínio. Também é possível conceder direitos e permissões do administrador exigidos para adicionar funções do servidor a uma conta do usuário. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) na documentação de implantação do servidor Standard Edition ou Enterprise Edition. Para outras alterações na configuração, apenas a associação no grupo RTCUniversalServerAdmins é necessária.

Se você definiu sua topologia de borda quando definiu e publicou sua topologia interna, e nenhuma alteração for necessária para a topologia de borda que você definiu anteriormente, não será necessário defini-la e publicá-la novamente. Use o procedimento a seguir somente caso seja necessário fazer alterações em sua topologia de borda. Você deve tornar a topologia previamente definida e publicada disponível para os servidores de borda, que você faz usando o procedimento em [exportar sua topologia do Lync Server 2013 e copiá-la para a mídia externa para instalação de borda](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).

<div>


> [!IMPORTANT]  
> Não é possível executar o construtor de topologias de um servidor de borda. Você deve executá-lo do seu Servidor Front-End ou servidores do Standard Edition.



</div>

O processo para definir a topologia do servidor de borda é feito no construtor de topologias. os três tipos principais de topologias de servidor de borda que você pode planejar e configurar são listados a seguir:

  - Para definir a topologia de um único servidor de borda

  - Para definir a topologia de um pool de servidor de borda de balanceamento de carga

  - Para definir a topologia de um pool de borda com carga de hardware balanceada

<div>

## <a name="to-define-the-topology-for-a-single-edge-server"></a>Para definir a topologia para um único Servidor de Borda

1.  Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.

2.  Na árvore de console, expanda o site no qual você deseja implantar um Servidor de Borda.

3.  Clique com o botão direito do mouse em **pools de borda**e clique em **novo pool de borda**.

4.  Em **Definir o Novo Pool de Borda**, clique em **Avançar**.

5.  Em **Definir o FQDN do pool de borda**, faça o seguinte:
    
      - Em **FQDN do Pool**, digite o FQDN (nome de domínio totalmente qualificado) da interface interna do Servidor de Borda.
        
        <div>
        

        > [!IMPORTANT]  
        > O nome especificado pode você deve ser idêntico ao nome de computador configurado no servidor. Por padrão, o nome de um computador que não é atribuído a um domínio é um nome curto, não um FQDN. O Construtor de Topologia utiliza FQDNs, não nomes curtos. Portanto, configure um sufixo DNS no nome do computador a ser implantado como um servidor de borda e que não esteja em um domínio. Use apenas caracteres padrões (incluindo A–Z, a–z, 0–9 e hífens) quando atribuir FQDNs a seus Lync Servers, Servidores de Borda e pools. Não use caracteres Unicode e sublinhados. Os caracteres não padrões em um FQDN frequentemente não são suportados pelo DNS externo e CAs públicos (quando o FQDN deve ser atribuído para o SN no certificado). Para obter detalhes sobre como adicionar um sufixo DNS a um nome de computador, consulte <A href="lync-server-2013-configure-dns-for-edge-support.md">Configurar o DNS para suporte de borda no Lync Server 2013</A>.

        
        </div>
    
      - Clique em **Pool de computador único** e em **Avançar**.

6.  Em **Selecionar recursos**, faça o seguinte:
    
      - Se você planeja usar um único FQDN e endereço IP para o serviço de acesso SIP, o serviço de Webconferência do Lync Server 2013 e os serviços de borda de A/V, marque a caixa de seleção **usar um único FQDN e endereço IP** .
    
      - Caso planeje habilitar a federação, marque a caixa de seleção **Habilitar federação para este pool de Borda (porta 5061)**
        
        <div>
        

        > [!NOTE]  
        > Você pode selecionar esta opção, mas somente um pool de Borda ou Servidor de Borda em sua organização pode ser publicado externamente para federação. Todo o acesso por usuários federados, incluindo as mensagens instantâneas públicas de usuários, percorrem o mesmo pool de borda ou um único servidor de borda. Por exemplo, se sua implantação incluir um pool de Borda ou um único Servidor de Borda implantado em Nova York e um implantado em Londres e você ativar o suporte à federação no pool de Borda de Nova York ou no Servidor de Borda único, o tráfego de sinal para os usuários federados passará através do pool de Borda de Nova York ou do Servidor de Borda único. Isso se aplica mesmo para a comunicação com os usuários de Londres, embora um usuário interno de Londres que chama um usuário federado de Londres use o pool de Londres ou o Servidor de Borda para um tráfego de A/V.

        
        </div>
    
      - Caso planeje oferecer suporte ao protocolo XMPP em sua implantação, marque a caixa de seleção **Habilitar federação XMPP (porta 5269)**

7.  Em **Selecionar Opções de IP**, faça o seguinte:
    
      - **Habilitar IPv4 na interface interna**: marque a caixa de seleção se quiser aplicar um endereço IPv4 à interface interna do servidor de borda ou do pool de borda
    
      - **Habilitar IPv6 na interface interna**: marque a caixa de seleção se quiser aplicar um endereço IPv6 à interface interna do servidor de borda ou do pool de borda
    
      - **Habilitar IPv4 na interface externa**: marque a caixa de seleção se quiser aplicar um endereço IPv4 à interface externa do servidor de borda ou do pool de borda
    
      - **Habilitar IPv6 na interface externa**: marque a caixa de seleção se quiser aplicar um endereço IPv6 à interface externa do servidor de borda ou do pool de borda
    
    Você também pode configurar o servidor de borda ou o pool de borda para usar um endereço de conversão de endereço de rede para endereços IP externos. Faça isso marcando a caixa de seleção **O endereço IP externo desse pool de Borda é convertido pelo NAT**.

8.  Em **FQDNs Externos**, faça o seguinte:
    
      - Se em **Selecionar recursos** você escolher usar um FQDN único e o endereço IP para o acesso SIP, o serviço de Conferência Web e um serviço de borda A/V, digite o FQDN externo em **Acesso SIP**.
        
        <div>
        

        > [!NOTE]  
        > Se você escolher esta opção, deverá especificar um número de porta diferente para cada um dos serviços de borda (configurações de porta recomendadas: 5061 para serviço de Acesso de Borda, 444 para serviço de Borda de Conferência Web e 443 para serviço de Borda A/V). Esta opção pode ajudar a evitar possíveis problemas de conectividade e simplificar a configuração porque você pode usar o mesmo número de porta (por exemplo, 443) para os três serviços.

        
        </div>
    
      - Se em **Selecionar recursos** você não escolheu usar um FQDN e endereço IP único, digite os FQDNs externo para o **Acesso SIP**,   **Conferência Web** e **Áudio vídeo**, mantendo as portas padrão.

9.  Clique em **Avançar**.

10. Em **Definir o endereço IP interno**, digite o endereço IP do seu Servidor de Borda em **Endereço IPv4 interno** e **Endereço IPv6 interno** conforme apropriado para seus requisitos. Clique em **Avançar**.

11. Em **Definir endereço IP externo**, faça o seguinte:
    
      - Caso opte por usar um único FQDN e endereço IP para o acesso SIP, serviço de Webconferência e serviço de borda A/V, digite o endereço IPv4 externo do servidor de borda em **Acesso SIP** e clique em **Avançar**.
    
      - Caso opte por usar endereços IPv6, digite o endereço IPv6 externo do servidor de borda em **Acesso SIP** e clique em **Avançar**.
    
      - Se você não escolheu usar um FQDN e endereço IP único para o acesso SIP, o serviço de Webconferência e o serviço de Borda A/V, digite os endereços IPv4 externos do Servidor de Borda em **Acesso SIP**, **Webconferência** e **Conferência A/V**, e clique em **Avançar**.
    
      - Se você optou por usar endereços IPv6 e não escolheu usar um FQDN e endereço IPv6 único para o acesso SIP, o serviço de Webconferência e o serviço de Borda A/V, digite os endereços IP externos do Servidor de Borda em **Acesso SIP**, **Webconferência** e **Conferência A/V**, e clique em **Avançar**.
        
        <div>
        

        > [!NOTE]  
        > Caso não tenha optado por habilitar e atribuir endereços IPv6, você não verá esta caixa de diálogo.

        
        </div>

12. Se você optou por usar NAT, uma caixa de diálogo será aberta. Em **Endereço IPv4 público para o serviço de Borda A/V**, digite o endereço IPv4 público a ser convertido pelo NAT e clique em **Avançar**.
    
    <div>
    

    > [!NOTE]  
    > Esse endereço deve ser o endereço IP externo do serviço de Borda A/V.

    
    </div>

13. Se você optou por usar NAT e endereços IPv6, uma caixa de diálogo será aberta. Em **Endereço IPv6 público para o serviço de Borda A/V**, digite o endereço IPv6 público a ser convertido pelo NAT e clique em **Avançar**.
    
    <div>
    

    > [!NOTE]  
    > Esse endereço deve ser o endereço IP externo do serviço de Borda. A/V.

    
    </div>

14. Em **Definir o próximo salto**, em **Próximo pool de salto**, selecione o nome do pool interno, que pode ser um pool de Front-Ends ou um pool do Standard Edition. Em alternativa, se sua implantação incluir um Diretor, selecione o Diretor e clique em **Avançar**.

15. Em **Associar pools de Front-Ends**, especifique um ou mais pools internos, que podem incluir pools de Front-Ends e servidores Standard Edition, para serem associados com este Servidor de Borda selecionando os nomes dos pools internos que devem usar este Servidor de Borda para comunicação com os usuários externos suportados.
    
    <div>
    

    > [!NOTE]  
    > Apenas um pool de Borda com carga balanceada ou um Servidor de Borda exclusivo pode ser associado a cada pool interno para o tráfego A/V. Se você já possui um pool interno associado a um pool de Borda ou Servidor de Borda, um aviso é exibido indicando que o pool interno já esteja associado com um pool de Borda ou um Servidor de Borda. Se você selecionar um pool já associado com outro servidor de borda, a associação será alterada.

    
    </div>

16. Clique em **Concluir**.

17. Publique sua topologia.

</div>

<div>

## <a name="to-define-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>Para definir a topologia para um pool de Servidor de Borda com balanceamento de carga de DNS

1.  Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.

2.  Na árvore do console, expanda o site em que deseja implantar Servidores de Borda.

3.  Clique com o botão direito em **Pools de Borda** e clique em **Novo Pool de Borda**.

4.  Em**Definir o Novo Pool de Borda**, clique em **Avançar**.

5.  Em **Definir o FQDN do pool de Borda**, faça o seguinte:
    
      - Em **FQDN do pool**, digite o nome de domínio totalmente qualificado (FQDN) para a conexão interna do pool de Borda.
        
        <div>
        

        > [!IMPORTANT]  
        > O nome especificado para o pool deve ser o nome do pool de borda interno. Ele deve ser definido como um FQDN. O Construtor de Topologia utiliza FQDNs, não nomes curtos. Use apenas caracteres padrões (incluindo A–Z, a–z, 0–9 e hífens) ao atribuir FQDNs dos seus Lync Servers, Servidores de Borda e pools. Não use caracteres Unicode e sublinhados. Muitas vezes, o DNS externo e as autoridades de certificação públicas não oferecem suporte a caracteres diferentes do padrão em um FQDN (quando o FQDN deve ser atribuído ao SN no certificado).

        
        </div>
    
      - Clique em **Pool de vários computadores** e, em seguida, clique em **Avançar**.

6.  Em **Selecionar recursos**, faça o seguinte:
    
      - Se você planeja usar um único FQDN e endereço IP para o acesso SIP, o serviço de Webconferência do Lync Server 2013 e os serviços de borda de A/V, marque a caixa de seleção **usar um único FQDN e endereço IP** .
    
      - Se você planeja habilitar a federação, marque a caixa de seleção **Habilitar federação para este pool de Borda (porta 5061)**. Clique em **Avançar**.
        
        <div>
        

        > [!NOTE]  
        > Você pode selecionar esta opção, mas somente um pool de Borda ou Servidor de Borda em sua organização pode ser publicado externamente para federação. Todo o acesso por usuários federados, incluindo sistemas de mensagens instantâneas (IM) públicos, passam pelo mesmo pool de Borda ou Servidor de Borda único. Por exemplo, se sua implantação inclui um pool de Borda ou Servidor de Borda único implantado em Nova York e um implantado em Londres e você habilitar o suporte a federação no pool de Borda de Nova York ou no Servidor de Borda único, o tráfego do sinal para usuários federados passará pelo pool de Borda de Nova York ou Servidor de Borda único. Isto é verdade mesmo para comunicações com usuários de Londres, embora um usuário interno de Londres ligando para um usuário federado de Londres use o pool desta cidade ou o Servidor de Borda para tráfego de A/V.

        
        </div>
    
      - Caso planeje oferecer suporte ao protocolo XMPP em sua implantação, marque a caixa de seleção **Habilitar federação XMPP (porta 5269)**

7.  Clique em **Avançar**.

8.  Em **Selecionar Opções de IP**, faça o seguinte:
    
      - **Habilitar IPv4 na interface interna**: marque a caixa de seleção se quiser aplicar um endereço IPv4 à interface interna do servidor de borda ou do pool de borda
    
      - **Habilitar IPv6 na interface interna**: marque a caixa de seleção se quiser aplicar um endereço IPv6 à interface interna do servidor de borda ou do pool de borda
    
      - **Habilitar IPv4 na interface externa**: marque a caixa de seleção se quiser aplicar um endereço IPv4 à interface externa do servidor de borda ou do pool de borda
    
      - **Habilitar IPv6 na interface externa**: marque a caixa de seleção se quiser aplicar um endereço IPv6 à interface externa do servidor de borda ou do pool de borda
    
    Você também pode configurar o servidor de borda ou o pool de borda para usar um endereço de conversão de endereço de rede para endereços IP externos. Faça isso marcando a caixa de seleção **O endereço IP externo desse pool de Borda é convertido pelo NAT**.

9.  Em **FQDNs Externos**, faça o seguinte:
    
      - Se em **Selecionar recursos** você optou por usar um único FQDN e Endereço IP para o acesso SIP, serviço de Webconferências e serviço de Borda de A/V, digite o FQDN externo em **Acesso SIP**.
        
        <div>
        

        > [!NOTE]  
        > Se você escolher esta opção, deverá especificar um número de porta diferente para cada um dos serviços de borda (configurações de porta recomendadas: 5061 para serviço de Acesso de Borda, 444 para serviço de Borda de Conferência Web e 443 para serviço de Borda A/V). Esta opção pode ajudar a evitar possíveis problemas de conectividade e simplificar a configuração porque você pode usar o mesmo número de porta (por exemplo, 443) para os três serviços.

        
        </div>
    
      - Se em **Selecionar recursos** você não optou por usar um único FQDN e Endereço IP, digite o FQDN escolhido para o lado voltado ao público do pool de borda em **Acesso SIP**. Em **Webconferências**, digite o FQDN escolhido para o lado voltado ao público do pool de Borda. Em **Áudio/Vídeo**, digite o FQDN escolhido para o lado voltado ao público do pool de Borda. Use as portas padrão.

10. Clique em **Avançar**.

11. Em **Definir computadores neste pool**, clique em **Adicionar**.

12. Em **FQDN e endereço IP internos**, faça o seguinte:
    
      - Em **Endereço IPv4 interno**, digite o endereço IPv4 e o  **Endereço IPv6 interno** conforme apropriado para seus requisitos para o primeiro servidor de borda que deseja criar no pool.
    
      - Em **FQDN Interno**, digite o FQDN do primeiro Servidor de Borda que deseja criar neste pool.
        
        <div>
        

        > [!NOTE]  
        > O nome especificado deve ser idêntico ao nome do computador configurado no servidor. Por padrão, o nome de computador de um computador que não faz parte de um domínio é um nome curto, não um FQDN. O Construtor de Topologia utiliza FQDNs, não nomes curtos. Portanto, você deve configurar um sufixo DNS no nome do computador para ser implantado como um Servidor de Borda que não é vinculado a um domínio. Use apenas caracteres padrões (incluindo A–Z, a–z, 0–9 e hífens) quando atribuir FQDNs a seus Lync Servers, Servidores de Borda, pools e matrizes. Não use caracteres Unicode ou sublinhados. Os caracteres não padrões em um FQDN frequentemente não são suportados pelo DNS externo e CAs públicos (quando o FQDN deve ser atribuído para o SN no certificado). Para obter detalhes sobre como adicionar um sufixo DNS a um nome de computador, consulte <A href="lync-server-2013-configure-dns-for-edge-support.md">Configurar o DNS para suporte de borda no Lync Server 2013</A>.

        
        </div>

13. Clique em **Avançar**.

14. Em **Definir endereços IP externos**, faça o seguinte:
    
      - Se você escolher usar um FQDN único e Endereço IP para o acesso SIP, o serviço de Webconferência e o serviço de Borda A/V, digite o endereço IP externo do Servidor de Borda em **Acesso SIP**.
    
      - Se você não escolher usar um FQDN único e Endereço IP para o acesso SIP, o serviço de Webconferência e o serviço de Conferência A/V, digite o endereço IP escolhido para o lado público deste servidor de pool de Borda para o **Acesso SIP**. Em **Webconferência**, digite o endereço IP escolhido para o lado público deste servidor de pool de Borda. Em **Conferência A/V**, digite o endereço IP escolhido para seu lado público deste servidor de pool de Borda.

15. Clique em **Avançar**.

16. Caso opte por habilitar endereços IPv6, em **Definir endereços IP externos**, faça o seguinte:
    
      - Se você optou por usar um único FQDN e Endereço IPv6 para o acesso SIP, serviço de Webconferências e serviço de Borda de A/V, digite o endereço IP externo do Servidor de Borda em **Acesso SIP**.
    
      - Se você não optou por usar um único FQDN e Endereço IP para o acesso SIP, serviço de Webconferências e serviço de Conferências de A/V, digite o endereço IPv6 escolhido para o lado voltado ao público deste servidor de pool de Borda no **Acesso SIP**. Em **Webconferências**, digite o endereço IPv6 escolhido para o lado voltado ao público deste servidor de pool de Borda. Em **Conferências de A/V**, digite o endereço IPv6 escolhido para o lado voltado ao público deste servidor de pool de Borda.
    
    <div>
    

    > [!NOTE]  
    > Caso não tenha optado por habilitar e atribuir endereços IPv6, você não verá esta caixa de diálogo.

    
    </div>

17. Clique em **Concluir**.
    
    <div>
    

    > [!NOTE]  
    > Você verá agora o primeiro Servidor de Borda criado no seu pool na caixa de diálogo <STRONG>Definir os computadores neste pool</STRONG>.

    
    </div>

18. Em **Definir os computadores neste pool**, clique em **Adicionar** e repita as etapas 11 até 14 para o segundo Servidor de Borda que deseja adicionar ao seu pool de Borda.

19. Após repetir as etapas 11 a 14, clique em **Avançar** em **Definir os computadores neste pool**.
    
    <div>
    

    > [!NOTE]  
    > Nesse ponto, é possível ver os dois Servidores de Borda em seu pool.

    
    </div>

20. Se você optou por usar NAT, uma caixa de diálogo será aberta. Em **Endereço IP público**, digite o endereço IPv4 e IPv6 público (se apropriado) a ser convertido pelo NAT e clique em **Avançar**.
    
    <div>
    

    > [!NOTE]  
    > Este deve ser o endereço IP externo da Borda de A/V.

    
    </div>

21. Em **Definir o próximo salto**, na lista **Próximo pool de salto**, selecione o nome do pool interno, que pode ser um pool de Front-Ends ou um pool do Standard Edition. Em alternativa, se sua implantação inclui um Diretor, selecione o nome do Diretor. Clique em **Avançar**.

22. Em **Associar pools de front-ends**, especifique um ou mais pools internos, que podem incluir pools de Front-Ends e servidores do Standard Edition, para serem associados a este Servidor de Borda selecionando os nomes dos pools internos que devem usar este Servidor de Borda para comunicação com os usuários externos suportados.
    
    <div>
    

    > [!NOTE]  
    > Apenas um pool de Borda com carga balanceada ou um Servidor de Borda exclusivo pode ser associado com cada pool interno para o tráfego A/V. Se você já possui um pool interno associado a um pool de Borda ou Servidor de Borda, um aviso é exibido indicando que o pool interno já está associado a um pool de Borda ou um Servidor de Borda. Se você selecionar um pool já associado a outro servidor de borda, associação será alterada.

    
    </div>

23. Clique em **Concluir**.

24. Publique sua topologia.

</div>

<div>

## <a name="to-define-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>Para definir a topologia de um pool de Servidor de Borda com balanceamento de carga de hardware

1.  Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.

2.  Na árvore de console, expanda o site no qual você deseja implantar os Servidores de Borda.

3.  Clique com o botão direito do mouse em **pools de borda**e selecione **novo pool de borda**.

4.  Em **Definir o Novo Pool de Borda**, clique em **Avançar**.

5.  Em **Definir o FQDN do pool de borda**, faça o seguinte:
    
      - Em **FQDN**, digite o FQDN (nome de domínio totalmente qualificado) escolhido para o lado interno do pool de borda.
        
        <div>
        

        > [!IMPORTANT]  
        > O nome especificado para o pool deve ser o nome do pool de borda interno. Ele deve ser definido como um FQDN. O Construtor de Topologia utiliza FQDNs, não nomes curtos. Use apenas caracteres padrões (incluindo A–Z, a–z, 0–9 e hífens) ao atribuir FQDNs dos seus Lync Servers, Servidores de Borda e pools. Não use caracteres Unicode ou sublinhados. Os caracteres não padrões em um FQDN frequentemente não são suportados pelo DNS externo e CAs públicos (quando o FQDN deve ser atribuído para o SN no certificado).

        
        </div>
    
    <!-- end list -->
    
      - Clique em **pool de vários computadores**e, em seguida, em **Avançar**.

6.  Em **Selecionar recursos**, faça o seguinte:
    
      - Se você planeja usar um único FQDN e endereço IP para o serviço de acesso SIP, o serviço de conferência da Web do Lync Server e o serviço de borda A/V, marque a caixa de seleção **usar um único FQDN & endereço IP** .
    
      - Se você planeja habilitar a federação, marque a caixa de seleção **Habilitar federação (para esse pool de Borda (porta 5061)**.
        
        <div>
        

        > [!NOTE]  
        > Você pode selecionar esta opção, mas somente um pool de Borda ou Servidor de Borda em sua organização pode ser publicado externamente para federação. Todo o acesso por usuários federados, incluindo as mensagens instantâneas públicas de usuários, percorrem o mesmo pool de Borda ou um único Servidor de Borda. Por exemplo, se sua implantação inclui um pool de Borda ou único Servidor de Borda implantado em Nova York e um implantado em Londres e você ativar o suporte à federação no pool de Borda de Nova York ou no Servidor de Borda único, o tráfego de sinal para os usuários federados passará através do pool de Borda de Nova York ou do Servidor de Borda único. Isso se aplica mesmo para a comunicação com os usuários de Londres, embora um usuário interno de Londres que chama um usuário federado de Londres use o pool de Londres ou o Servidor de Borda para um tráfego de A/V.

        
        </div>
    
      - Caso planeje oferecer suporte ao protocolo XMPP em sua implantação, marque a caixa de seleção **Habilitar federação XMPP (porta 5269)**

7.  Clique em **Avançar**.

8.  Em **Selecionar Opções de IP**, faça o seguinte:
    
      - **Habilitar IPv4 na interface interna**: marque a caixa de seleção se quiser aplicar um endereço IPv4 à interface interna do servidor de borda ou do pool de borda
    
      - **Habilitar IPv6 na interface interna**: marque a caixa de seleção se quiser aplicar um endereço IPv6 à interface interna do servidor de borda ou do pool de borda
    
      - **Habilitar IPv4 na interface externa**: marque a caixa de seleção se quiser aplicar um endereço IPv4 à interface externa do servidor de borda ou do pool de borda
    
      - **Habilitar IPv6 na interface externa**: marque a caixa de seleção se quiser aplicar um endereço IPv6 à interface externa do servidor de borda ou do pool de borda
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>Não</STRONG> marque a caixa de seleção <STRONG>O endereço IP externo do pool de Borda é convertido pelo NAT</STRONG>. A NAT (conversão de endereços de rede) não é suportada quando você está usando o balanceamento de carga de hardware.

    
    </div>

9.  Em **FQDNs externos**, faça o seguinte:
    
      - Se em **Selecionar recursos** você escolher usar um FQDN único e o endereço IP para o acesso SIP, o serviço de Webconferência e um serviço de Borda A/V, digite o FQDN externo em **Acesso SIP**.
        
        <div>
        

        > [!NOTE]  
        > Se você escolher esta opção, deverá especificar um número de porta diferente para cada um dos serviços de borda (configurações de porta recomendadas: 5061 para serviço de Acesso de Borda, 444 para serviço de Borda de Conferência Web e 443 para serviço de Borda A/V). Esta opção pode ajudar a evitar possíveis problemas de conectividade e simplificar a configuração porque você pode usar o mesmo número de porta (por exemplo, 443) para os três serviços.

        
        </div>
    
      - Se em **Selecionar recursos** você não optou por usar um único FQDN e Endereço IP, digite o FQDN escolhido para o lado voltado ao público do pool de borda em **Acesso SIP**. Em **Webconferências**, digite o FQDN escolhido para o lado voltado ao público do pool de Borda. Em **Áudio/Vídeo**, digite o FQDN escolhido para o lado voltado ao público do pool de Borda. Use as portas padrão.
        
        <div>
        

        > [!NOTE]  
        > Estes serão os FQDNs de IP virtual (VIP) voltados ao público para o pool.

        
        </div>

10. Clique em **Avançar**.

11. Em **Definir os computadores neste pool**, clique em **Adicionar**.

12. Em **Definir os endereços IP externos**, faça o seguinte:
    
      - Caso opte por usar um único FQDN e endereço IP para o acesso SIP, serviço de Webconferência e serviço de borda A/V, digite o endereço IPv4 externo do servidor de borda em **Acesso SIP**.endereço IP externo do servidor de borda em **Acesso SIP**.
    
      - Se você não optou por usar um único FQDN e Endereço IP para o acesso SIP, serviço de Webconferências e serviço de Conferências de A/V, digite o endereço IP escolhido para o lado voltado ao público deste servidor de pool de Borda no **Acesso SIP**. Em **Webconferências**, digite o endereço IP escolhido para o lado voltado ao público deste servidor de pool de Borda. Em **Conferências de A/V**, digite o endereço IP escolhido para o lado voltado ao público deste servidor de pool de Borda.

13. Clique em **Avançar**.

14. Caso opte por habilitar endereços IPv6, em **Definir endereços IP externos**, faça o seguinte:
    
      - Se você optou por usar um único FQDN e Endereço IPv6 para o acesso SIP, serviço de Webconferências e serviço de Borda de A/V, digite o endereço IP externo do Servidor de Borda em **Acesso SIP**.
    
      - Se você não optou por usar um único FQDN e Endereço IP para o acesso SIP, serviço de Webconferências e serviço de Conferências de A/V, digite o endereço IPv6 escolhido para o lado voltado ao público deste servidor de pool de Borda no **Acesso SIP**. Em **Webconferências**, digite o endereço IPv6 escolhido para o lado voltado ao público deste servidor de pool de Borda. Em **Conferências de A/V**, digite o endereço IPv6 escolhido para o lado voltado ao público deste servidor de pool de Borda.
    
    <div>
    

    > [!NOTE]  
    > Caso não tenha optado por habilitar e atribuir endereços IPv6, você não verá esta caixa de diálogo.

    
    </div>

15. Clique em **Concluir**.
    
    <div>
    

    > [!NOTE]  
    > Você verá agora o primeiro Servidor de Borda criado no seu pool na caixa de diálogo <STRONG>Definir os computadores neste pool</STRONG>.

    
    </div>

16. Em **Definir os computadores deste pool**, clique em **Adicionar** e repita as etapas de 11 a 14 para o segundo Servidor de Borda que você deseja adicionar ao pool de Borda.

17. Após repetir as etapas 11 a 14, clique em **Avançar** em **Definir os computadores neste pool**.
    
    <div>
    

    > [!NOTE]  
    > Nesse ponto, é possível ver os dois Servidores de Borda em seu pool.

    
    </div>

18. Em **Definir o próximo salto**, na lista **Próximo pool de salto**, selecione o nome do pool interno, que pode ser um pool de Front-Ends ou um pool do Standard Edition. Em alternativa, se sua implantação inclui um Diretor, selecione o nome do Diretor. Clique em **Avançar**.

19. Em **Associar pools de front-ends**, especifique um ou mais pools internos, que podem incluir pools de Front-Ends e servidores do Standard Edition, para serem associados a este Servidor de Borda selecionando os nomes dos pools internos que devem usar este Servidor de Borda para comunicação com os usuários externos suportados.
    
    <div>
    

    > [!NOTE]  
    > Apenas um pool de Borda com carga balanceada ou um Servidor de Borda exclusivo pode ser associado com cada pool interno para o tráfego A/V. Se você já possui um pool interno associado a um pool de Borda ou Servidor de Borda, um aviso é exibido indicando que o pool interno já está associado a um pool de Borda ou um Servidor de Borda. Se você selecionar um pool já associado a outro servidor de borda, associação será alterada.

    
    </div>

20. Clique em **Concluir**.

21. Publique sua topologia.

</div>

</div>

<span> </span>

</div>

</div>

</div>

