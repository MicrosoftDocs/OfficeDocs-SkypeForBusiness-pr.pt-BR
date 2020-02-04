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
ms.openlocfilehash: 4a04dca4b935caf8f07546babd2c53f65fff4e89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-your-edge-topology-in-lync-server-2013"></a>Definir sua topologia de borda no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-28_

Você deve usar o construtor de topologias para criar sua topologia e deve configurar pelo menos um pool de front-end interno ou um servidor Standard Edition para poder implantar o servidor de borda. Use o procedimento a seguir para definir a topologia de borda para um único servidor de borda e, em seguida, use os procedimentos em [publicar sua topologia no Lync server 2013](lync-server-2013-publish-your-topology.md) e [exportar sua topologia do Lync Server 2013 e copiá-la para a mídia externa para a instalação do Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) para publicar a topologia e disponibilizá-la para o servidor de borda.

<div>


> [!NOTE]  
> As interfaces de Borda interna e externa precisam usar o mesmo tipo de balanceamento de carga. Não é possível usar balanceamento de carga DNS em uma interface de Borda e balanceamento de carga de hardware na outra interface de Borda.



</div>

Para publicar, habilitar ou desabilitar uma topologia com êxito ao adicionar ou remover uma função de servidor, você deve estar conectado como um usuário que é membro do grupo RTCUniversalServerAdmins e administradores do domínio. Você também pode conceder direitos e permissões de administrador necessários para adicionar funções de servidor a uma conta de usuário. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) na documentação de implantação do servidor Standard Edition ou Enterprise Edition Server. Para outras alterações de configuração, somente a associação no grupo RTCUniversalServerAdmins é necessária.

Se você definiu a topologia de borda quando definiu e publicou sua topologia interna, e nenhuma alteração é necessária para a topologia de borda que você definiu anteriormente, você não precisa defini-la e publicá-la novamente. Use o procedimento a seguir somente se precisar fazer alterações na sua topologia de borda. Você deve disponibilizar a topologia previamente definida e publicada para seus servidores de borda, usando o procedimento em [exportar sua topologia do Lync Server 2013 e copiá-la para a mídia externa para instalação do Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).

<div>


> [!IMPORTANT]  
> Não é possível executar o construtor de topologias a partir de um servidor de borda. Você deve executá-lo a partir de seu servidor front-end ou servidores Standard Edition.



</div>

O processo para definir a topologia do servidor de borda é feito no construtor de topologias. Os três tipos principais de topologias de servidor de borda que você planeja e configura estão listados abaixo:

  - Para definir a topologia para um servidor de borda único

  - Para definir a topologia de um pool de servidores de borda com balanceamento de carga

  - Para definir a topologia de um pool de bordas com carga balanceada de hardware

<div>

## <a name="to-define-the-topology-for-a-single-edge-server"></a>Para definir a topologia para um servidor de borda único

1.  Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.

2.  Na árvore de console, expanda o site no qual você deseja implantar um servidor de borda.

3.  Clique com o botão direito do mouse em **conjuntos de bordas**e clique em **novo pool de bordas**.

4.  Em **definir o novo pool de bordas**, clique em **Avançar**.

5.  Em **definir o FQDN do pool de bordas**, faça o seguinte:
    
      - Em **pool FQDN**, digite o nome de domínio totalmente qualificado (FQDN) da interface interna do servidor de borda.
        
        <div>
        

        > [!IMPORTANT]  
        > O nome que você especificar dever ser idêntico ao nome de computador configurado no servidor. Por padrão, o nome do computador de um computador que não está associado a um domínio é um nome curto, e não um FQDN. O Construtor de Topologias usa FQDNs, não nomes curtos. Portanto, você deverá configurar um sufixo DNS no nome do computador a ser implantado no Servidor de Borda que não ingressou no domínio. Use apenas caracteres padrão (incluindo A–Z, a–z, 0–9 e hifens) ao atribuir FQDNs de seus Lync Servers, Servidores de Borda e pools. Não use caracteres Unicode ou sublinhados. Os caracteres não padrão em um FQDN geralmente não são compatíveis com o DNS externo e CAs públicas (quando o FQDN deve ser atribuído ao SN no certificado). Para obter detalhes sobre como adicionar um sufixo DNS a um nome de computador, consulte <A href="lync-server-2013-configure-dns-for-edge-support.md">Configurar o DNS para suporte de borda no Lync Server 2013</A>.

        
        </div>
    
      - Clique em **pool de computador único**e, em seguida, clique em **Avançar**.

6.  Em **selecionar recursos**, faça o seguinte:
    
      - Se você pretende usar um único FQDN e um único endereço IP para o serviço de acesso SIP, serviço de Webconferência do Lync Server 2013 e os/V Edge Services, marque a caixa de seleção **usar um único FQDN e endereço IP** .
    
      - Se você planeja habilitar a Federação, marque a caixa de seleção **habilitar Federação para este pool de bordas (porta 5061)** .
        
        <div>
        

        > [!NOTE]  
        > Você pode selecionar essa opção, mas somente um pool de bordas ou um servidor de borda em sua organização pode ser publicado externamente para Federação. Todo o acesso de usuários federados, incluindo usuários públicos de mensagens instantâneas (IM), passam pelo mesmo pool de bordas ou servidor de borda única. Por exemplo, se sua implantação inclui um pool de bordas ou um servidor de borda única implantado em Nova York e um implantado em Londres e você habilitar o suporte de Federação no pool de bordas de Nova York ou no servidor de borda único, o tráfego de sinal para usuários federados passará pela Nova York Pool de bordas ou servidor de borda único. Isso se aplica inclusive para comunicações com usuários de Londres, embora um usuário interno de Londres chamando um usuário federado de Londres use o pool de Londres ou Servidor de Borda para tráfego de A/V.

        
        </div>
    
      - Se você planeja dar suporte ao protocolo de mensagens extensíveis e presença (XMPP) para a sua implantação, marque a caixa de seleção **habilitar Federação de XMPP (porta 5269)**

7.  Em **selecionar opções de IP**, faça o seguinte:
    
      - **Habilitar IPv4 na interface interna**: marque a caixa de seleção se desejar aplicar um endereço IPv4 à interface interna do servidor de borda ou do pool de bordas
    
      - **Habilitar o IPv6 na interface interna**: marque a caixa de seleção se desejar aplicar um endereço IPv6 à interface interna do servidor de borda ou do pool de bordas
    
      - **Habilitar IPv4 na interface externa**: marque a caixa de seleção se desejar aplicar um endereço IPv4 à interface externa do servidor de borda ou do pool de bordas
    
      - **Habilitar o IPv6 em uma interface externa**: marque a caixa de seleção se desejar aplicar um endereço IPv6 à interface externa do servidor de borda ou do pool de bordas
    
    Você também pode configurar o servidor de borda ou o pool de bordas para usar um endereço de conversão de endereços de rede para os endereços IP externos. Para fazer isso, marque a caixa de seleção **o endereço IP externo deste pool de bordas é convertido pela NAT**.

8.  Em **FQDNs externos**, faça o seguinte:
    
      - Se, em **Selecione os recursos** , você optar por usar um único FQDN e um único endereço IP para o acesso SIP, serviço de Webconferência e a/V Edge, digite o FQDN externo no **acesso SIP**.
        
        <div>
        

        > [!NOTE]  
        > Se você escolher essa opção, especifique um número de porta diferente para cada um dos serviços de borda (configurações de porta recomendadas: 5061 para serviço de borda de acesso, 444 para serviço de borda de Webconferência e 443 para serviço de borda A/V). Selecionar essa opção pode ajudar a evitar possíveis problemas de conectividade e simplificar a configuração porque você pode usar o mesmo número de porta (por exemplo, 443) para todos os três serviços.

        
        </div>
    
      - Se, **em Selecione os recursos** , você não tiver optado por usar um único FQDN e endereço IP, digite os FQDNs externos para **acesso SIP**, **conferência na Web** e **vídeo de áudio**, mantendo as portas padrão.

9.  Click **Next**.

10. Em **definir o endereço IP interno**, digite o endereço IP do seu servidor de borda em **endereço IPv4 interno** e **endereço IPv6 interno** como apropriado para seus requisitos. Click **Next**.

11. Em **definir o endereço IP externo**, faça o seguinte:
    
      - Se você optou por usar um único FQDN e um único endereço IP para o acesso SIP, serviço de Webconferência e A/V Edge, digite o endereço IPv4 externo do servidor de borda no **acesso SIP**e clique em **Avançar**.
    
      - Se você optou por usar endereços IPv6, digite o endereço IPv6 externo do servidor de borda em **acesso SIP**e clique em **Avançar**.
    
      - Se você não optou por usar um único FQDN e um único endereço IP para o acesso SIP, serviço de Webconferência e a/V Edge, digite os endereços IPv4 externos do servidor de borda no **acesso SIP**, **conferência via Web**e **conferência a/v**e, em seguida, clique em **Avançar**.
    
      - Se você optou por usar endereços IPv6 e não optou por usar um único FQDN e um único endereço IP para o acesso SIP, serviço de Webconferência e a/V Edge, digite os endereços IPv6 externos do servidor de borda em **acesso SIP**, **conferência via Web**e **conferência a/v**e clique em **Avançar**.
        
        <div>
        

        > [!NOTE]  
        > Se você não optou por habilitar e atribuir endereçamento IPv6, esta caixa de diálogo não será exibida.

        
        </div>

12. Se você optou por usar o NAT, será exibida uma caixa de diálogo. Em **endereço IPv4 público para o serviço de borda a/V**, digite o endereço IPv4 público a ser traduzido por Nat e clique em **Avançar**.
    
    <div>
    

    > [!NOTE]  
    > Este deve ser o endereço IP externo do serviço de borda A/V.

    
    </div>

13. Se você optou por usar o NAT e endereços IPv6, será exibida uma caixa de diálogo. Em **endereço IPv6 público para o serviço de borda a/V**, digite o endereço IPv6 público a ser traduzido por Nat e clique em **Avançar**.
    
    <div>
    

    > [!NOTE]  
    > Este deve ser o endereço IP externo do serviço de borda A/V.

    
    </div>

14. Em **definir o próximo salto**, no **próximo pool de saltos**, selecione o nome do pool interno, que pode ser um pool de front-ends ou um pool padrão de edição. Ou, se a sua implantação incluir um director, selecione o diretor. Em seguida, clique em **Avançar**.

15. Em **pools de front-end**, especifique um ou mais pools internos, que podem incluir pools front-ends e servidores Standard Edition, a serem associados a esse servidor de borda, selecionando os nomes dos pools internos que devem usar esse servidor de borda para comunicação com usuários externos com suporte.
    
    <div>
    

    > [!NOTE]  
    > Somente um pool de bordas com carga balanceada ou um servidor de borda única pode ser associado a cada pool interno para o tráfego A/V. Se você já tiver um pool interno associado a um pool de bordas ou servidor de borda, um aviso será exibido indicando que o pool interno já está associado a um pool de bordas ou um servidor de borda. Se você selecionar um pool que já esteja associado a outro servidor de borda, ele alterará a associação.

    
    </div>

16. Clique em **Concluir**.

17. Publicar sua topologia.

</div>

<div>

## <a name="to-define-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>Para definir a topologia de um pool de servidores de borda balanceada para carga de DNS

1.  Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.

2.  Na árvore de console, expanda o site no qual você deseja implantar servidores de borda.

3.  Clique com o botão direito do mouse em **conjuntos de bordas**e clique em **novo pool de bordas**.

4.  Em **definir o novo pool de bordas**, clique em **Avançar**.

5.  Em **definir o FQDN do pool de bordas**, faça o seguinte:
    
      - Em **pool FQDN**, digite o nome de domínio totalmente qualificado (FQDN) para a conexão interna do pool de borda.
        
        <div>
        

        > [!IMPORTANT]  
        > O nome que você especificar para o pool deve ser o nome do pool de bordas internas. Isso deve ser definido como um FQDN. O Construtor de Topologias usa FQDNs, não nomes curtos. Use apenas caracteres padrão (incluindo A–Z, a–z, 0–9 e hifens) ao atribuir FQDNs de seus Lync Servers, Servidores de Borda e pools. Não use caracteres Unicode ou sublinhados. Os caracteres não padrão em um FQDN geralmente não são compatíveis com o DNS externo e CAs públicas (quando o FQDN deve ser atribuído ao SN no certificado).

        
        </div>
    
      - Clique em **vários pools de computador**e clique em **Avançar**.

6.  Em **selecionar recursos**, faça o seguinte:
    
      - Se você pretende usar um único FQDN e endereço IP para o acesso SIP, serviço de Webconferência do Lync Server 2013 e serviços de borda A/V, marque a caixa de seleção **usar um único FQDN e endereço IP** .
    
      - Se você planeja habilitar a Federação, marque a caixa de seleção **habilitar Federação para este pool de bordas (porta 5061)** . Clique em **Avançar**
        
        <div>
        

        > [!NOTE]  
        > Você pode selecionar essa opção, mas somente um pool de bordas ou um servidor de borda em sua organização pode ser publicado externamente para Federação. Todo o acesso de usuários federados, incluindo usuários públicos de mensagens instantâneas (IM), passam pelo mesmo pool de bordas ou servidor de borda única. Por exemplo, se sua implantação incluir um pool de Borda ou um único Servidor de Borda implantado em Nova York e outro implantado em Londres e você habilitar o suporte para federação no pool de Borda de Nova York ou único Servidor de Borda, o tráfego do sinal para usuários federados passará pelo pool de Borda ou único Servidor de Borda de Nova York. Isso se aplica inclusive para comunicações com usuários de Londres, embora um usuário interno de Londres chamando um usuário federado de Londres use o pool de Londres ou Servidor de Borda para tráfego de A/V.

        
        </div>
    
      - Se você planeja dar suporte ao protocolo de mensagens extensíveis e presença (XMPP) para a sua implantação, marque a caixa de seleção **habilitar Federação de XMPP (porta 5269)**

7.  Click **Next**.

8.  Em **selecionar opções de IP**, faça o seguinte:
    
      - **Habilitar IPv4 na interface interna**: marque a caixa de seleção se desejar aplicar um endereço IPv4 à interface interna do servidor de borda ou do pool de bordas
    
      - **Habilitar o IPv6 na interface interna**: marque a caixa de seleção se desejar aplicar um endereço IPv6 à interface interna do servidor de borda ou do pool de bordas
    
      - **Habilitar IPv4 na interface externa**: marque a caixa de seleção se desejar aplicar um endereço IPv4 à interface externa do servidor de borda ou do pool de bordas
    
      - **Habilitar o IPv6 em uma interface externa**: marque a caixa de seleção se desejar aplicar um endereço IPv6 à interface externa do servidor de borda ou do pool de bordas
    
    Você também pode configurar o servidor de borda ou o pool de bordas para usar um endereço de conversão de endereços de rede para os endereços IP externos. Para fazer isso, marque a caixa de seleção **o endereço IP externo deste pool de bordas é convertido pela NAT**.

9.  Em **FQDNs externos**, faça o seguinte:
    
      - Se, em **Selecione os recursos** , você optar por usar um único FQDN e um único endereço IP para o acesso SIP, serviço de Webconferência e a/V Edge, digite o FQDN externo no **acesso SIP**.
        
        <div>
        

        > [!NOTE]  
        > Se você escolher essa opção, especifique um número de porta diferente para cada um dos serviços de borda (configurações de porta recomendadas: 5061 para serviço de borda de acesso, 444 para serviço de borda de Webconferência e 443 para serviço de borda A/V). Ao selecionar essa opção, você pode ajudar a evitar possíveis problemas de conectividade e simplificar a configuração porque pode usar o mesmo número de porta (por exemplo, 443) para todos os três serviços.

        
        </div>
    
      - Se, em **Selecione os recursos** , você não tiver optado por usar um único FQDN e endereço IP, digite o FQDN escolhido para seu lado público do pool de bordas no **acesso SIP**. Em **Webconferência**, digite o FQDN escolhido para o seu lado público do lado do pool de borda. Em **áudio/vídeo**, digite o FQDN escolhido para seu lado público do lado do pool de borda. Use as portas padrão.

10. Click **Next**.

11. Em **definir os computadores neste pool**, clique em **Adicionar**.

12. Em **endereço IP e FQDN internos**, faça o seguinte:
    
      - Em **endereço IPv4 interno**, digite o endereço IPv4 e o **endereço IPv6 interno** como apropriado para seus requisitos para o primeiro servidor de borda que você deseja criar nesse pool.
    
      - Em **FQDN interno**, digite o FQDN do primeiro servidor de borda que você deseja criar nesse pool.
        
        <div>
        

        > [!NOTE]  
        > O nome que você especificar dever ser idêntico ao nome de computador configurado no servidor. Por padrão, o nome de computador de um computador que não faz parte de um domínio é um nome curto, não um FQDN. O Construtor de Topologias usa FQDNs, não nomes curtos. Portanto, você deverá configurar um sufixo DNS no nome do computador a ser implantado no Servidor de Borda que não ingressou no domínio. Use somente caracteres padrão (incluindo A – Z, A – z, 0 – 9 e hifens) ao atribuir FQDNs dos seus servidores, servidores de borda, pools e matrizes do Lync. Não use caracteres Unicode ou sublinhados. Os caracteres não padrão em um FQDN geralmente não são compatíveis com o DNS externo e CAs públicas (quando o FQDN deve ser atribuído ao SN no certificado). Para obter detalhes sobre como adicionar um sufixo DNS a um nome de computador, consulte <A href="lync-server-2013-configure-dns-for-edge-support.md">Configurar o DNS para suporte de borda no Lync Server 2013</A>.

        
        </div>

13. Click **Next**.

14. Em **definir os endereços IP externos**, faça o seguinte:
    
      - Se você optou por usar um único FQDN e um único endereço IP para o acesso SIP, serviço de Webconferência e a/V Edge, digite o endereço IP externo do servidor de borda no **acesso SIP**.
    
      - Se você não optou por usar um único FQDN e um único endereço IP para o serviço de acesso SIP, Web de Webconferência e o/V referencing, digite o endereço IP que você escolheu para o seu lado público deste servidor de pool de borda para **acesso SIP**. Em **Webconferência**, digite o endereço IP que você escolheu para o seu lado público deste servidor de pool de borda. Em **conferência A/V**, digite o endereço IP escolhido para o seu lado público do lado público deste servidor de pool de borda.

15. Click **Next**.

16. Se você optou por habilitar endereços IPv6, em **definir os endereços IP externos**, faça o seguinte:
    
      - Se você optou por usar um único FQDN e um único endereço IP para o acesso SIP, serviço de Webconferência e a/V Edge, digite o endereço IPv6 externo do servidor de borda no **acesso SIP**.
    
      - Se você não optou por usar um único FQDN e um único endereço IP para o serviço de acesso SIP, Web de Webconferência e o/V referencing, digite o endereço IPv6 que você escolheu para o seu lado público deste servidor de pool de borda para **acesso SIP**. Em **Webconferência**, digite o endereço IPv6 que você escolheu para seu lado público do lado público deste servidor de pool de borda. Em **conferência A/V**, digite o endereço IPv6 que você escolheu para seu lado público do lado público deste servidor de pool de borda.
    
    <div>
    

    > [!NOTE]  
    > Se você não optou por habilitar e atribuir endereçamento IPv6, esta caixa de diálogo não será exibida.

    
    </div>

17. Clique em **Concluir**.
    
    <div>
    

    > [!NOTE]  
    > Agora, você verá o primeiro servidor de borda que você criou no pool na caixa de diálogo <STRONG>definir os computadores neste pool</STRONG> .

    
    </div>

18. Em **definir os computadores nesse pool**, clique em **Adicionar**e, em seguida, repita as etapas 11 a 14 para o segundo servidor de borda que você deseja adicionar ao seu pool de bordas.

19. Após repetir as etapas 11 a 14, clique em **Avançar** em **definir os computadores nesse pool**.
    
    <div>
    

    > [!NOTE]  
    > Nesse ponto, você pode ver os dois servidores de borda no pool.

    
    </div>

20. Se você optou por usar o NAT, será exibida uma caixa de diálogo. Em **endereço IP público**, digite os endereços IPv4 e IPv6 públicos (conforme apropriado) a serem convertidos por Nat e clique em **Avançar**.
    
    <div>
    

    > [!NOTE]  
    > Deve ser o endereço IP externo da borda A/V.

    
    </div>

21. Em **definir o próximo salto**, na lista **próximo pool de saltos** , selecione o nome do pool interno, que pode ser um pool de front-ends ou um pool padrão de edição. Ou, se a sua implantação incluir um director, selecione o nome do diretor. Em seguida, clique em **Avançar**.

22. Em **pools de front-end**, especifique um ou mais pools internos, que podem incluir pools front-ends e servidores Standard Edition, a serem associados a esse servidor de borda, selecionando os nomes dos pools internos que serão usados neste servidor de borda para comunicação com usuários externos com suporte.
    
    <div>
    

    > [!NOTE]  
    > Somente um pool de bordas com carga balanceada ou um servidor de borda única pode ser associado a cada pool interno para o tráfego A/V. Se você já tiver um pool interno associado a um pool de bordas ou servidor de borda, um aviso será exibido indicando que o pool interno já está associado a um pool de bordas ou um servidor de borda. Se você selecionar um pool que já esteja associado a outro servidor de borda, ele alterará a associação.

    
    </div>

23. Clique em **Concluir**.

24. Publicar sua topologia.

</div>

<div>

## <a name="to-define-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>Para definir a topologia de um pool de servidores de borda com carga balanceada de hardware

1.  Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.

2.  Na árvore de console, expanda o site no qual você deseja implantar servidores de borda.

3.  Clique com o botão direito do mouse em **conjuntos de bordas**e selecione **novo pool de bordas**.

4.  Em **definir o novo pool de bordas**, clique em **Avançar**.

5.  Em **definir o FQDN do pool de bordas**, faça o seguinte:
    
      - Em **FQDN**, digite o nome de domínio totalmente qualificado (FQDN) escolhido para o lado interno do pool de bordas.
        
        <div>
        

        > [!IMPORTANT]  
        > O nome que você especificar para o pool deve ser o nome do pool de bordas internas. Isso deve ser definido como um FQDN. O Construtor de Topologias usa FQDNs, não nomes curtos. Use apenas caracteres padrão (incluindo A–Z, a–z, 0–9 e hifens) ao atribuir FQDNs de seus Lync Servers, Servidores de Borda e pools. Não use caracteres Unicode ou sublinhados. Os caracteres não padrão em um FQDN geralmente não são compatíveis com o DNS externo e CAs públicas (quando o FQDN deve ser atribuído ao SN no certificado).

        
        </div>
    
    <!-- end list -->
    
      - Clique em **vários pool de computador**e, em seguida, em **Avançar**.

6.  Em **selecionar recursos** , faça o seguinte:
    
      - Se você pretende usar um único FQDN e endereço IP para o serviço de acesso SIP, serviço de Webconferência do Lync Server e A/V Edge, marque a caixa de seleção **usar um único fqdn & endereço IP** .
    
      - Se você planeja habilitar a Federação, marque a caixa de seleção **habilitar Federação para este pool de bordas (porta 5061)** .
        
        <div>
        

        > [!NOTE]  
        > Você pode selecionar essa opção, mas somente um pool de bordas ou um servidor de borda em sua organização pode ser publicado externamente para Federação. Todo o acesso de usuários federados, incluindo usuários públicos de mensagens instantâneas (IM), passam pelo mesmo pool de bordas ou servidor de borda única. Por exemplo, se sua implantação incluir um pool de Borda ou um único Servidor de Borda implantado em Nova York e outro implantado em Londres e você habilitar o suporte para federação no pool de Borda de Nova York ou único Servidor de Borda, o tráfego do sinal para usuários federados passará pelo pool de Borda ou único Servidor de Borda de Nova York. Isso se aplica inclusive para comunicações com usuários de Londres, embora um usuário interno de Londres chamando um usuário federado de Londres use o pool de Londres ou Servidor de Borda para tráfego de A/V.

        
        </div>
    
      - Se você planeja dar suporte ao protocolo de mensagens extensíveis e presença (XMPP) para a sua implantação, marque a caixa de seleção **habilitar Federação de XMPP (porta 5269)**

7.  Click **Next**.

8.  Em **selecionar opções de IP**, faça o seguinte:
    
      - **Habilitar IPv4 na interface interna**: marque a caixa de seleção se desejar aplicar um endereço IPv4 à interface interna do servidor de borda ou do pool de bordas
    
      - **Habilitar o IPv6 na interface interna**: marque a caixa de seleção se desejar aplicar um endereço IPv6 à interface interna do servidor de borda ou do pool de bordas
    
      - **Habilitar IPv4 na interface externa**: marque a caixa de seleção se desejar aplicar um endereço IPv4 à interface externa do servidor de borda ou do pool de bordas
    
      - **Habilitar o IPv6 em uma interface externa**: marque a caixa de seleção se desejar aplicar um endereço IPv6 à interface externa do servidor de borda ou do pool de bordas
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>Não</STRONG> marque a caixa de seleção <STRONG>o endereço IP externo do pool de bordas é traduzido pela NAT</STRONG> . Não há suporte para a conversão de endereços de rede (NAT) quando você está usando o balanceamento de carga de hardware.

    
    </div>

9.  Em **FQDNs externos**, faça o seguinte:
    
      - Se, em **Selecione os recursos** , você optar por usar um único FQDN e um único endereço IP para o acesso SIP, serviço de Webconferência e a/V Edge, digite o FQDN externo no **acesso SIP**.
        
        <div>
        

        > [!NOTE]  
        > Se optar por selecionar essa opção, você deve especificar um número de porta diferente para cada um dos serviços de borda (configurações de porta recomendadas: 5061 para serviço de borda de acesso, 444 para serviço de borda de Webconferência e 443 para serviço de borda A/V). Ao selecionar essa opção, você pode ajudar a evitar possíveis problemas de conectividade e simplificar a configuração porque pode usar o mesmo número de porta (por exemplo, 443) para todos os três serviços.

        
        </div>
    
      - Se, em **Selecione os recursos** , você não tiver optado por usar um único FQDN e endereço IP, digite o FQDN escolhido para seu lado público do pool de bordas no **acesso SIP**. Em **Webconferência**, digite o FQDN escolhido para o seu lado público do lado do pool de borda. Em **áudio/vídeo**, digite o FQDN escolhido para seu lado público do lado do pool de borda. Use as portas padrão.
        
        <div>
        

        > [!NOTE]  
        > Estes serão os FQDNs VIP (IP virtual) de voltagem pública para o pool.

        
        </div>

10. Click **Next**.

11. Em **definir os computadores neste pool**, clique em **Adicionar**.

12. Em **definir os endereços IP externos**, faça o seguinte:
    
      - Se você optou por usar um único FQDN e um único endereço IP para o acesso SIP, serviço de Webconferência e a/V Edge, digite o endereço IPv4 externo do servidor de borda no **acesso SIP**. endereço IP externo do servidor de borda no **acesso SIP**.
    
      - Se você não optou por usar um único FQDN e um único endereço IP para o serviço de acesso SIP, Web de Webconferência e o/V referencing, digite o endereço IP que você escolheu para o seu lado público deste servidor de pool de borda para **acesso SIP**. Em **Webconferência**, digite o endereço IP que você escolheu para o seu lado público deste servidor de pool de borda. Em **conferência A/V**, digite o endereço IP escolhido para o seu lado público do lado público deste servidor de pool de borda.

13. Click **Next**.

14. Se você optou por habilitar endereços IPv6, em **definir os endereços IP externos**, faça o seguinte:
    
      - Se você optou por usar um único FQDN e um único endereço IP para o acesso SIP, serviço de Webconferência e a/V Edge, digite o endereço IPv6 externo do servidor de borda no **acesso SIP**.
    
      - Se você não optou por usar um único FQDN e um único endereço IP para o serviço de acesso SIP, Web de Webconferência e o/V referencing, digite o endereço IPv6 que você escolheu para o seu lado público deste servidor de pool de borda para **acesso SIP**. Em **Webconferência**, digite o endereço IPv6 que você escolheu para seu lado público do lado público deste servidor de pool de borda. Em **conferência A/V**, digite o endereço IPv6 que você escolheu para seu lado público do lado público deste servidor de pool de borda.
    
    <div>
    

    > [!NOTE]  
    > Se você não optou por habilitar e atribuir endereçamento IPv6, esta caixa de diálogo não será exibida.

    
    </div>

15. Clique em **Concluir**.
    
    <div>
    

    > [!NOTE]  
    > Agora, você verá o primeiro servidor de borda que você criou no pool na caixa de diálogo <STRONG>definir os computadores neste pool</STRONG> .

    
    </div>

16. Em **definir os computadores nesse pool**, clique em **Adicionar**e, em seguida, repita as etapas 11 a 14 para o segundo servidor de borda que você deseja adicionar ao seu pool de bordas.

17. Após repetir as etapas 11 a 14, clique em **Avançar** em **definir os computadores nesse pool**.
    
    <div>
    

    > [!NOTE]  
    > Nesse ponto, você pode ver os dois servidores de borda no pool.

    
    </div>

18. Em **definir o próximo salto**, na lista **próximo pool de saltos** , selecione o nome do pool interno, que pode ser um pool de front-ends ou um pool padrão de edição. Ou, se a sua implantação incluir um director, selecione o nome do diretor. Em seguida, clique em **Avançar**.

19. Em **pools de front-end**, especifique um ou mais pools internos, que podem incluir pools front-ends e servidores Standard Edition, a serem associados a esse servidor de borda, selecionando os nomes dos pools internos que serão usados neste servidor de borda para comunicação com usuários externos com suporte.
    
    <div>
    

    > [!NOTE]  
    > Somente um pool de bordas com carga balanceada ou um servidor de borda única pode ser associado a cada pool interno para o tráfego A/V. Se você já tiver um pool interno associado a um pool de bordas ou servidor de borda, um aviso será exibido indicando que o pool interno já está associado a um pool de bordas ou um servidor de borda. Se você selecionar um pool que já esteja associado a outro servidor de borda, ele alterará a associação.

    
    </div>

20. Clique em **Concluir**.

21. Publicar sua topologia.

</div>

</div>

<span> </span>

</div>

</div>

</div>

