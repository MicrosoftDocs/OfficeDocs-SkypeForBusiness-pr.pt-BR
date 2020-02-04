---
title: 'Lync Server 2013: configurar um tronco com bypass de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk with media bypass
ms:assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398792(v=OCS.15)
ms:contentKeyID: 48184959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16c12a5d8cff03f8d5755b5a2b54a6ff4dcf8399
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-with-media-bypass-in-lync-server-2013"></a>Configure a trunk with media bypass in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-02-07_

Siga estas etapas se desejar configurar um tronco com o bypass de mídia habilitado. Para configurar um tronco com bypass de mídia desabilitado, consulte [configurar um tronco sem bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md). O bypass de mídia é útil quando você deseja minimizar o número de servidores de mediação implantados. Geralmente, um pool de servidores de mediação será implantado em um site central, e ele controlará os gateways em sites de filiais. Habilitar o bypass de mídia permite que a mídia para chamadas PSTN de clientes em sites locais flua diretamente pelos gateways para estes sites. Os roteamentos de chamadas de saída do Lync Server 2013 e as políticas de voz corporativa devem ser configurados corretamente para que chamadas PSTN de clientes em um site de filial sejam roteadas para o gateway apropriado.

É altamente recomendável habilitar o bypass de mídia. No entanto, antes de habilitá-lo em um tronco SIP, confirme se seu provedor do tronco SIP oferece suporte ao bypass de mídia e pode acomodar os requisitos para habilitar o cenário com êxito. Especificamente, o provedor deve ter os endereços IP dos servidores na rede interna da sua organização. Se o provedor não puder dar suporte a esse cenário, o bypass de mídia não terá êxito. Para obter detalhes, consulte [planejando o bypass de mídia no Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) na documentação de planejamento.

<div>


> [!NOTE]  
> O bypass de mídia não interoperará com cada gateway PSTN (rede telefônica pública comutada), IP-PBX e controlador de borda de sessão (SBC). A Microsoft testou um conjunto de gateways PSTN e SBCs com os parceiros certificados e realizou alguns testes com IP-PBXs da Cisco. O bypass de mídia só tem suporte com produtos e versões listados no programa de interoperabilidade aberta da comunicação unificada – Lync Server em <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.



</div>

Uma configuração de tronco, como descrita abaixo, agrupa um conjunto de parâmetros que são aplicados a troncos atribuídos a essa configuração de tronco. O escopo de uma configuração de tronco específica pode ser global (para todos os troncos que não têm configuração de site ou pool mais específica), ou para um site ou pool. A configuração de tronco no nível do pool é usada para fazer o escopo de uma configuração de tronco específico para um único tronco.

<span id="BKMK_ConfigTrunkMediaBypassSteps"></span>

<div>

## <a name="to-configure-a-trunk-with-media-bypass"></a>Para configurar um tronco com bypass de mídia

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Roteamento de Voz** e depois, em **Configuração do Tronco**.

4.  Na página **Configuração do Tronco**, use um dos métodos a seguir para configurar um tronco:
    
      - Dê um duplo clique em um tronco existente (por exemplo, o tronco **Global**) para exibir a caixa de diálogo **Editar Configuração do Tronco**.
    
      - Clique em **Novo** e depois, selecione um escopo para a nova configuração de tronco:
        
          - **Tronco de site:** Escolha o site para esta configuração de tronco **Selecione um site**e clique em **OK**. Observe que se uma configuração de tronco já tiver sido criada para um site, o site não aparecerá em **Selecionar um Site**. Essa configuração de tronco será aplicada a todos os troncos no site.
        
          - **Tronco de pool:** Escolha o nome do tronco ao qual essa configuração de tronco se aplica. Esse tronco pode ser o tronco raiz ou qualquer tronco adicional definido no construtor de topologias. Em **Selecionar um Serviço**, clique em **OK**. Observe que se uma configuração de tronco já tiver sido criada para um tronco específico, o tronco não aparecerá em **Selecionar um Serviço**.
    
    <div>
    

    > [!NOTE]  
    > Depois de selecionar o escopo da configuração de tronco, ele não poderá ser alterado.<BR>O campo <STRONG>Nome</STRONG> é pré-preenchido com o nome do site ou serviço associado à configuração de tronco e não pode ser alterado.

    
    </div>

5.  Especifique um valor em **Máximo de caixas de diálogo iniciais com suporte**. Este é o número máximo de respostas bifurcadas que um gateway de rede de telefonia comutada pública (PSTN), IP-PBX, ou Controlador de Borda de Sessão (SBC) ITSP pode receber para um INVITE enviado para o Servidor de Mediação. O valor padrão é 20.
    
    <div>
    

    > [!NOTE]  
    > Antes de alterar este valor, consulte seu provedor de serviços ou fabricante do equipamento para detalhes sobre as capacidades do seu sistema.

    
    </div>

6.  Selecione uma das seguintes opções de **Nível de suporte de criptografia**:
    
      - **Obrigatório:** A criptografia do SRTP (protocolo de transporte em tempo real seguro) deve ser usada para ajudar a proteger o tráfego entre o servidor de mediação e o gateway ou PBX (Private Branch Exchange).
    
      - **Opcional:** A criptografia SRTP será usada se o provedor de serviços ou o fabricante de equipamento oferecer suporte a ele.
    
      - **Sem suporte:** A criptografia do SRTP não é compatível com o provedor de serviços ou com o fabricante do equipamento e, portanto, não será usada.

7.  Selecione a opção **Habilitar bypass de mídia** se você deseja que que a mídia desvie do Servidor de Mediação para processamento pelo ponto do tronco.
    
    <div>
    

    > [!IMPORTANT]  
    > Para que o bypass de mídia funcione com êxito, o gateway PSTN gateway, IP-PBX ou Controlador de Borda de Sessão ITSP deve oferecer suporte a determinados recursos. Para obter detalhes, consulte <A href="lync-server-2013-planning-for-media-bypass.md">planejando o bypass de mídia no Lync Server 2013</A> na documentação de planejamento.

    
    </div>

8.  Selecione a opção **Processamento de mídia centralizado** se houver um ponto de terminação de mídia conhecido (por exemplo, um gateway PSTN em que a terminação de mídia tem o mesmo IP da terminação de sinalização). Desmarque esta opção se o tronco não possuir um ponto de terminação de mídia conhecido.

9.  Se o par de troncos der suporte para receber solicitações de referência SIP do servidor de mediação, marque a caixa de seleção **habilitar o envio para o gateway** .
    
    <div>
    

    > [!NOTE]  
    > Se esta opção for desabilitada enquanto a opção <STRONG>Habilitar bypass de mídia</STRONG> estiver selecionada, configurações adicionais são necessárias. Se o ponto do tronco não oferecer suporte ao recebimento de solicitações SIP REFER do Servidor de Mediação e o bypass de mídia estiver habilitado, você também deve executar o cmdlet <STRONG>Set-CsTrunkConfiguration</STRONG> para desabilitar o RTCP para chamadas ativas e em espera para suportar as condições adequadas para bypass de mídia. Para obter detalhes, consulte a documentação do <A href="lync-server-2013-lync-server-management-shell.md">Shell de gerenciamento do Lync Server 2013</A> .<BR>Como alternativa, é possível selecionar <STRONG>Ativar referenciamento usando controle de chamada de terceiros</STRONG> se quiser que as chamadas transferidas contornem a mídia e o gateway não suporte solicitações SIP REFER.

    
    </div>

10. (Opcional) Para permitir roteamento entre troncos, associe e configure os registros de uso de PSTN a essa configuração de tronco. Os usos de PSTN associados a essa configuração de tronco serão aplicados a todas as chamadas de entrada por meio do tronco que não se originam de um ponto de extremidade do Lync. Para gerenciar os registros de uso de PSTN associados à configuração de tronco, use um dos métodos a seguir:
    
      - Para selecionar um ou mais registros de uma lista de todos os registros de uso PSTN disponíveis na sua implantação do Enterprise Voice, clique em **selecionar**. Realce os registros que você deseja associar a essa configuração de tronco e depois, clique em **OK**.
    
      - Para remover um registro de uso de PSTN desta configuração de tronco, selecione o registro e clique em **Remover**.
    
      - Para definir um novo registro de uso PSTN e associá-lo a essa configuração de tronco, faça o seguinte:
        
        1.  Clique em **Novo**.
        
        2.  No campo **Nome**, especifique um nome descritivo que seja exclusivo para o registro.
            
            <div>
            

            > [!NOTE]  
            > O nome do registro de uso de PSTN deve ser exclusivo dentro de implantação do Enterprise Voice. Após a gravação do registro, o campo <STRONG>Nome</STRONG> não pode ser editado.

            
            </div>
        
        3.  Use um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:
            
              - Para selecionar uma ou mais rotas da lista de todas as rotas disponíveis na sua implantação do Enterprise Voice, clique em **selecionar**. Destaque as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.
            
              - Para remover uma rota do registro de uso do PSTN, selecione a rota e clique em **Remover**.
            
              - Para definir uma nova rota e associá-la ao registro de uso do PSTN, clique em **Novo**. Para obter detalhes, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Para editar uma rota que está associada a esse registro de uso do PSTN, selecione a rota e clique em **Exibir detalhes**. Para obter detalhes, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        4.  Clique em **OK**.
    
      - Para editar um registro de uso de PSTN que já está associado a essa configuração de tronco, faça o seguinte:
        
        1.  Selecione o registro de uso do PSTN que você deseja editar e clique em **Mostrar detalhes**.
        
        2.  Use um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:
            
              - Para selecionar uma ou mais rotas da lista de todas as rotas disponíveis na sua implantação do Enterprise Voice, clique em **selecionar**. Destaque as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.
            
              - Para remover uma rota do registro de uso do PSTN, selecione a rota e clique em **Remover**.
            
              - Para definir uma nova rota e associá-la ao registro de uso do PSTN, clique em **Novo**. Para obter detalhes, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Para editar uma rota que está associada a esse registro de uso do PSTN, selecione a rota e clique em **Exibir detalhes**. Para obter detalhes, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        3.  Clique em **OK**.
    
    <div>
    

    > [!IMPORTANT]  
    > É importante associar registros de uso PSTN de acordo com o peer do servidor de mediação associado ao tronco que está sendo configurado. Se o peer do servidor de mediação for um gateway PSTN ou um controle de borda de sessão (SBC), é altamente recomendável que a configuração de troncos não esteja associada a um registro de uso PSTN que roteia para um destino PSTN ou qualquer outro sistema downstream conectado via Lync Servidor.

    
    </div>

11. Organize os registros de uso do PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, selecione o registro de uso e clique na seta para cima ou para baixo.
    
    <div>
    

    > [!IMPORTANT]  
    > A ordem na qual PSTN registros de uso são listados na configuração de tronco é significativa. O Lync Server percorre a lista de cima para baixo.

    
    </div>

12. **Enable RTP Latching** deve ser selecionado para permitir desvio de mídia para clientes atrás de uma NAT (conversão de endereço de rede) ou firewall, e um SBC que suporte travamento.

13. **Habilitar o histórico de chamadas de encaminhamento** deve ser selecionado para permitir o envio de informações de histórico de chamadas para o par de gateways do servidor de mediação.

14. **Habilitar encaminhar os dados de identidades p-declarados** devem ser selecionados para permitir que as informações do originador da chamada p-Asserted-Identity (pai) sejam encaminhadas entre o lado do servidor de mediação e o lado do gateway (e vice-versa), quando estiverem presentes.

15. **Enable outbound routing failover timer** deve ser selecionado para permitir failover rápido. O gateway associado a esse tronco pode fornecer notificações em 10 segundos de que está processando uma chamada de saída. O redirecionamento para outro tronco ocorrerá se essa notificação não for recebida pelo servidor de mediação. Em redes onde a latência pode atrasar o tempo de resposta ou o gateway levar mais de 10 segundos para responder, o failover rápido deverá ser desativado.

16. (Opcional) Associe e configure as **regras de conversão do número de chamada** do tronco. Essas regras de conversão se aplicam ao número chamado para chamadas de saída.
    
      - Para escolher uma ou mais regras de uma lista de todas as regras de tradução que estão disponíveis na sua implantação do Enterprise Voice, clique em **selecionar**. Em **Selecionar Regras de Conversão**, clique nas regras que você deseja associar com o tronco, e depois em **OK**.
    
      - Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**. Para obter detalhes sobre como definir uma nova regra, consulte [definindo regras de tradução no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.
    
      - Para editar uma regra de conversão que já esteja associada ao tronco, clique no nome da regra e clique em **Exibir detalhes**. Para obter detalhes, consulte [definindo regras de tradução no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.
    
      - Para copiar uma regra de conversão existente para usar como ponto de partida para definir uma nova regra, clique no nome da regra e clique em **Copiar** e clique em **Copiar**. Para obter detalhes, consulte [definindo regras de tradução no Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em **Remover**.
    
    <div>
    

    > [!WARNING]  
    > Não associe regras de conversão a um tronco se não houver regras de conversão configuradas no ponto do tronco associado porque as duas regras podem entrar em conflito.

    
    </div>

17. (Opcional) Associe e configure as **regras de conversão de números chamados** do tronco. As regras de conversão se aplicam ao número chamado em uma chamada de saída.
    
      - Para escolher uma ou mais regras de uma lista de todas as regras de tradução que estão disponíveis na sua implantação do Enterprise Voice, clique em **selecionar**. Em **Selecionar Regras de Conversão**, clique nas regras que você deseja associar com o tronco, e depois em **OK**.
    
      - Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**. Para obter detalhes sobre como definir uma nova regra, consulte [definindo regras de tradução no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.
    
      - Para editar uma regra de conversão que já esteja associada ao tronco, clique no nome da regra e clique em **Exibir detalhes**. Para obter detalhes, consulte [definindo regras de tradução no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.
    
      - Para copiar uma regra de conversão existente para usar como ponto de partida para definir uma nova regra, clique no nome da regra e clique em **Copiar** e clique em **Copiar**. Para obter detalhes, consulte [definindo regras de tradução no Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em **Remover**.
    
    <div>
    

    > [!WARNING]  
    > Não associe regras de conversão a um tronco se não houver regras de conversão configuradas no ponto do tronco associado porque as duas regras podem entrar em conflito.

    
    </div>

18. Verifique se as regras de conversão do tronco estão organizadas na ordem correta. Para alterar a posição de uma regra na lista, realce o nome da regra e clique na seta para cima ou para baixo.
    
    <div>
    

    > [!IMPORTANT]  
    > O Lync Server 2013 percorre a lista de regras de tradução da parte superior para baixo e usa a primeira regra que corresponde ao número discado. Se você configurar um tronco de forma que um número discado possa corresponder a mais de uma regra de conversão, certifique-se de que as regras mais restritivas estejam classificadas acima das regras menos restritivas. Por exemplo, se você incluiu uma regra de conversão que corresponda a qualquer número de 11 dígitos e uma regra de conversão que corresponda somente a números de 11 dígitos que comecem com +1425, certifique-se de que a regra que corresponda a qualquer número de 11 dígitos esteja classificada <EM>abaixo</EM> da regra mais restritiva.

    
    </div>

19. Ao terminar de configurar o tronco, clique em **OK**.

20. Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**.
    
    <div>
    

    > [!NOTE]  
    > Sempre que criar ou modificar uma configuração de tronco, você deve executar o comando <STRONG>Confirmar tudo</STRONG> para publicar a alteração na configuração. Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</A> na documentação de operações.

    
    </div>

Depois de configurar o tronco, continue a configuração do bypass de mídia escolhendo entre as opções de bypass de mídia global, conforme descrito em [Opções de bypass de mídia global no Lync Server 2013](lync-server-2013-global-media-bypass-options.md) na documentação de implantação.

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurar um tronco sem bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  


[Configurar bypass de mídia no Lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Opções de bypass de mídia global no Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  


[Definindo regras de tradução no Lync Server 2013](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

