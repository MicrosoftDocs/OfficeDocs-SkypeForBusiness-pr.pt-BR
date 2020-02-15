---
title: 'Lync Server 2013: configurar um tronco sem bypass de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk without media bypass
ms:assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425831(v=OCS.15)
ms:contentKeyID: 48183825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd810c64f546c907f0fd00d2dc2fea43e09fa1bf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-without-media-bypass-in-lync-server-2013"></a>Configurar um tronco sem bypass de mídia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-24_

Se quiser configurar um tronco com desvio de mídia desabilitado, siga estas etapas. Se quiser configurar um tronco com bypass de mídia habilitado, consulte [configurar um tronco com bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).

Uma configuração de tronco, como descrito abaixo, agrupa um conjunto de parâmetros que são aplicados a troncos designados com essa configuração. Uma determinada configuração de tronco pode ter o escopo de forma global (a todos os troncos que não têm uma configuração de site ou pool mais específica), para um site ou para um pool. A configuração de tronco no nível do pool é usada para definir o escopo de uma configuração específica de um tronco individual.

<span id="BKMK_ConfigTrunkGenericSteps"></span>

<div>

## <a name="to-configure-a-trunk-without-media-bypass"></a>Para configurar um tronco sem bypass de mídia

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em **Configuração de Tronco**.

4.  Na página **Configuração de Tronco**, use um dos seguintes métodos para configurar um tronco:
    
      - Clique duas vezes em um tronco existente (por exemplo, o tronco **Global**) para exibir a caixa de diálogo **Editar Configuração de Tronco**.
    
      - Clique em **Novo** e selecione um escopo para a nova configuração do tronco:
        
          - **Tronco de site:** Escolha o site para essa configuração de tronco em **selecionar um site** e clique em **OK**. Observe que se uma configuração de tronco já tiver sido criada para um site, o site não aparecerá em **Selecionar um Site**. Essa configuração de tronco será aplicada a todos os troncos do site.
        
          - **Tronco do pool:** Escolha o nome do tronco ao qual essa configuração de tronco se aplica em **Selecione um serviço** e clique em **OK**. Esse tronco pode ser o tronco raiz ou qualquer tronco adicional definido no construtor de topologias. Observe que se uma configuração de tronco já tiver sido criada para um tronco específico, esse tronco não será exibido em **Selecionar um Serviço**.
    
    <div>
    

    > [!NOTE]  
    > Depois de selecionar o escopo da configuração do tronco, não será possível alterá-lo.<BR>O campo <STRONG>Nome</STRONG> é preenchido previamente com o nome do site ou serviço associado à configuração do tronco e não pode ser alterado.

    
    </div>

5.  Selecione uma das seguintes opções de **Nível de suporte de criptografia**:
    
      - **Obrigatório:** A criptografia SRTP (Secure real-time Transport Protocol) deve ser usada para ajudar a proteger o tráfego entre o servidor de mediação e o gateway ou PBX (Private Branch Exchange).
    
      - **Opcional:** A criptografia SRTP será usada se o provedor de serviços ou o fabricante do equipamento oferecer suporte a ela.
    
      - **Sem suporte:** A criptografia SRTP não é suportada pelo provedor de serviços ou fabricante do equipamento e, portanto, não será usada.

6.  Certifique-se de que a caixa de seleção **Habilitar bypass de mídia** esteja desmarcada.

7.  Marque a caixa de seleção **Processamento de mídia centralizado** se houver um ponto de encerramento de mídia conhecido [por exemplo, um gateway PSTN (Rede Telefônica Pública Comutada) no qual o encerramento de mídia tenha o mesmo IP que o encerramento de sinalização]. Desmarque essa caixa de seleção se o tronco não tiver um ponto de encerramento de mídia conhecido.

8.  Se o par de troncos suportar o recebimento de solicitações SIP REFEREntes ao servidor de mediação, marque a caixa de seleção **habilitar o envio se refere ao gateway** .

9.  (Opcional) Para habilitar o roteamento entre troncos, associe e configure os registros de uso de PSTN a essa configuração de tronco. Os usos de PSTN associados a essa configuração de tronco serão aplicados a todas as chamadas recebidas pelo tronco que não foram originadas em um ponto de extremidade do Lync. Para gerenciar registros de uso de PSTN associados a uma configuração de tronco, use um dos seguintes métodos:
    
      - Para selecionar um ou mais registros de uma lista de todos os registros de uso de PSTN disponíveis em sua implantação do Enterprise Voice, clique em **selecionar**. Destaque os registros que deseja associar a essa configuração de tronco e clique em **OK**.
    
      - Para remover um registro de uso de PSTN dessa configuração de tronco, selecione-o e clique em **Remover**.
    
      - Para definir um novo registro de uso de PSTN e associá-lo a essa configuração de tronco, faça o seguinte:
        
        1.  Clique em **Novo**.
        
        2.  No campo **Nome**, especifique um nome descritivo exclusivo para o registro.
            
            <div>
            

            > [!NOTE]  
            > O nome do registro de uso do PSTN deve ser exclusivo dentro de implantação do Enterprise Voice. Após a gravação do registro, o campo <STRONG>Nome</STRONG> não pode ser editado.

            
            </div>
        
        3.  Use um dos seguintes métodos para associar e configurar rotas a esse registro de uso de PSTN:
            
              - Para selecionar uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **selecionar**. Destaque as rotas que deseja associar a esse registro de uso de PSTN e clique em **OK**.
            
              - Para remover uma rota do registro de uso de PSTN, selecione-a a clique em **Remover**.
            
              - Para definir uma nova rota e associá-la a essa registro de uso de PSTN, clique em **Novo**. Para obter detalhes, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Para editar uma rota associada a esse registro de uso de PSTN, selecione-a e clique em **Mostrar detalhes**. Para obter detalhes, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        4.  Clique em **OK**.
    
      - Para editar um registro de uso de PSTN que já está associado a essa configuração de tronco, faça o seguinte:
        
        1.  Selecione o registro de uso de PSTN que deseja editar e clique em **Mostrar detalhes**.
        
        2.  Use um dos seguintes métodos para associar e configurar rotas a esse registro de uso de PSTN:
            
              - Para selecionar uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **selecionar**. Destaque as rotas que deseja associar a esse registro de uso de PSTN e clique em **OK**.
            
              - Para remover uma rota do registro de uso de PSTN, selecione-a a clique em **Remover**.
            
              - Para definir uma nova rota e associá-la a essa registro de uso de PSTN, clique em **Novo**. Para obter detalhes, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Para editar uma rota associada a esse registro de uso de PSTN, selecione-a e clique em **Mostrar detalhes**. Para obter detalhes, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        3.  Clique em **OK**.
    
    <div>
    

    > [!IMPORTANT]  
    > É importante associar registros de uso do PSTN de acordo com o ponto do servidor de mediação associado ao tronco que está sendo configurado. Se o ponto de servidor de mediação for um gateway PSTN ou um SBC (controlador de borda de sessão), é altamente recomendável que a configuração de tronco não esteja associada a um registro de uso de PSTN que roteia um destino PSTN ou qualquer outro sistema downstream conectado via Lync Do.

    
    </div>

10. Organize os registros de uso de PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, selecione esse registro de uso de PSTN e clique nas setas para cima ou para baixo.
    
    <div>
    

    > [!IMPORTANT]  
    > A ordem em que os registros de uso de PSTN são listados na configuração de tronco é importante. O Lync Server percorre a lista de cima para baixo.

    
    </div>

11. **Habilitar engatador RTP** deve ser selecionado para habilitar bypass de mídia para clientes sob um NAT ou firewall e um SBC que dê suporte ao engatador.

12. **Habilitar o histórico de chamadas de encaminhamento** deve ser selecionado para habilitar o envio de informações de histórico de chamadas para o par de gateway do servidor de mediação.

13. **Habilitar os dados de encaminhamento P-Asserted-Identity** devem ser selecionados para permitir que as informações do originador de chamadas do pai sejam encaminhadas entre o lado do servidor de mediação e o lado do gateway (e vice-versa), quando presentes.

14. **Habilitar roteamento de saída do temporizador de failover** deve ser selecionado para habilitar um failover rápido. O gateway associado a esse tronco pode enviar notificações em 10 segundos sobre o processamento de uma chamada de saída. O redirecionamento para outro tronco ocorrerá se essa notificação não for recebida pelo servidor de mediação. Em redes nas quais a latência pode atrasar o tempo de resposta em mais de 10 segundos, o failover rápido deve ser desabilitado.

15. (Opcional) Associe e configure **regras de conversão de número de chamada** ao tronco. Essas regras de conversão se aplicam ao número de chamada das chamadas de saída.
    
      - Para escolher uma ou mais regras de uma lista de todas as regras de conversão que estão disponíveis em sua implantação do Enterprise Voice, clique em **selecionar**. Em **Selecionar Regras de Conversão**, clique nas regras que deseja associar ao tronco e clique em **OK**.
    
      - Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**. Para obter detalhes sobre como definir uma nova regra, consulte [definindo regras de conversão no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.
    
      - Para editar uma regra de conversão que já está associada ao tronco, clique no nome da regra e, depois, em **Mostrar detalhes**. Para obter detalhes, consulte [definindo regras de conversão no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.
    
      - Para copiar uma regra de conversão existente a fim de usá-la como ponto de partida para definir uma nova regra, clique no nome da regra, em seguida, em **Copiar** e, então, clique em **Colar**. Para obter detalhes, consulte [definindo regras de conversão no Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em **Remover **.
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="segurança" alt="security" />Observação de segurança:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Não associe regras de conversão a um tronco se você tiver configurado as regras de conversão no ponto de tronco associado, pois as duas regras podem entrar em conflito.</td>
    </tr>
    </tbody>
    </table>
    
    </div>

16. (Opcional) Associe e configure **regras de conversão de número chamado** ao tronco. As regras de conversão se aplicam ao número chamado de uma chamada de saída.
    
      - Para escolher uma ou mais regras de uma lista de todas as regras de conversão que estão disponíveis em sua implantação do Enterprise Voice, clique em **selecionar**. Em **Selecionar Regras de Conversão**, clique nas regras que deseja associar ao tronco e clique em **OK**.
    
      - Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**. Para obter detalhes sobre como definir uma nova regra, consulte [definindo regras de conversão no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.
    
      - Para editar uma regra de conversão que já está associada ao tronco, clique no nome da regra e, depois, em **Mostrar detalhes**. Para obter detalhes, consulte [definindo regras de conversão no Lync Server 2013](lync-server-2013-defining-translation-rules.md) na documentação de implantação.
    
      - Para copiar uma regra de conversão existente a fim de usá-la como ponto de partida para definir uma nova regra, clique no nome da regra, em seguida, em **Copiar** e, então, clique em **Colar**. Para obter detalhes, consulte [definindo regras de conversão no Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em **Remover **.
    
    <div>
    

    > [!WARNING]  
    > Não associe regras de conversão a um tronco se você tiver configurado as regras de conversão no ponto de tronco associado, pois as duas regras podem entrar em conflito.

    
    </div>

17. Certifique-se de que as regras de conversão do tronco estejam organizadas na ordem correta. Para alterar a posição de uma regra na lista, destaque o nome da regra e clique na seta para cima ou para baixo.
    
    <div>
    

    > [!IMPORTANT]  
    > O Lync Server atravessa a lista de regras de conversão de cima para baixo e usa a primeira regra que corresponde ao número discado. Se você configurar um tronco de modo que um número discado possa corresponder a mais de uma regra de conversão, certifique-se de que as regras mais restritivas estejam classificadas acima das regras menos restritivas. Por exemplo, se tiver incluído uma regra de conversão que corresponda a qualquer número de 11 dígitos e uma regra de conversão que corresponda somente a números de 11 dígitos que comecem com +1425, certifique-se de que a regra que corresponde a qualquer número de 11 dígitos esteja classificada <EM>abaixo</EM> da regra mais restritiva.

    
    </div>

18. Depois de concluir a configuração do tronco, clique em **OK**.

19. Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**.
    
    <div>
    

    > [!NOTE]  
    > Sempre que você criar ou modificar uma configuração de tronco, execute o comando <STRONG>Confirmar tudo</STRONG> para publicar a alteração da configuração. Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending Changes to The Voice Routing Configuration in Lync Server 2013</A> na documentação operações.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurar um tronco com bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[Definindo regras de conversão no Lync Server 2013](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

