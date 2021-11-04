---
title: Skype for Business Server - Configurar um tronco com bypass de mídia
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Como configurar um tronco com bypass de mídia habilitado. "
ms.openlocfilehash: 40a3b991481a8cf9cfb26be8ad45aa97dccf261f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60739227"
---
# <a name="skype-for-business-server---configure-a-trunk-with-media-bypass"></a>Skype for Business Server - Configurar um tronco com bypass de mídia 

Siga estas etapas para configurar um tronco com bypass de mídia habilitado. Para configurar um tronco com bypass de mídia desabilitado, consulte [Configure a trunk without media bypass in Skype for Business Server](configure-a-trunk-without-media-bypass.md). O bypass de mídia é útil quando você deseja minimizar o número de Servidores de Mediação implantados. Geralmente, um pool de Servidores de Mediação será implantado em um site central e controlará os gateways em sites locais. Habilitar o bypass de mídia permite que a mídia para chamadas PSTN de clientes em sites locais flua diretamente pelos gateways para estes sites. Skype for Business Server de chamadas de saída e Enterprise Voice políticas devem ser configuradas corretamente para que as chamadas PSTN de clientes em um site de filial sejam roteadas para o gateway apropriado.

Recomendamos que você habilita o bypass de mídia. No entanto, antes de habilitar o bypass de mídia em um tronco SIP, confirme se o provedor de tronco SIP qualificado dá suporte ao bypass de mídia e é capaz de acomodar os requisitos para habilitar o cenário com êxito. Especificamente, o provedor deve ter os endereços IP dos servidores na rede interna da sua organização. Se o provedor não puder suportar esse cenário, o bypass de mídia não terá êxito. Para obter detalhes, consulte [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

> [!NOTE]
> O bypass de mídia não interopera com cada gateway PSTN (rede telefônica pública comutado), IP-PBX e Controlador de Borda de Sessão (SBC). A Microsoft testou um conjunto de gateways PSTN e SBCs com parceiros certificados e fez alguns testes com o Cisco IP-PBXs. O bypass de mídia só é suportado com produtos e versões listados na página Infraestrutura de [Telefonia para](../../../SfbPartnerCertification/certification/infra-gateways.md) Skype for Business Server. 


Uma configuração de tronco conforme descrito abaixo grupos um conjunto de parâmetros que são aplicados a troncos atribuídos a essa configuração de tronco. Uma determinada configuração de tronco pode ter o escopo de forma global (a todos os troncos que não têm uma configuração de site ou pool mais específica), para um site ou para um pool. A configuração de tronco no nível do pool é usada para definir o escopo de uma configuração específica de um tronco individual.

**Para configurar um tronco com bypass de mídia**

1. Abra Skype painel de controle do servidor busines.
2. Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em **Configuração de Tronco**.
3. Na página **Configuração de Tronco**, use um dos seguintes métodos para configurar um tronco:
    - Clique duas vezes em um tronco existente (por exemplo, o tronco **Global**) para exibir a caixa de diálogo **Editar Configuração de Tronco**.
    - Clique em **Novo** e selecione um escopo para a nova configuração do tronco:
        - **Tronco do** site : escolha o site para essa configuração de tronco **em Selecionar um Site** e clique em **OK**. Observe que se uma configuração de tronco já tiver sido criada para um site, o site não aparecerá em **Selecionar um Site**. Essa configuração de tronco será aplicada a todos os troncos do site.
        - **Tronco do pool**: escolha o nome do tronco ao qual essa configuração de tronco se aplica. Esse tronco pode ser o tronco raiz ou quaisquer troncos adicionais definidos no Construtor de Topologias. Em **Selecionar um Serviço,** clique em **OK**. Observe que se uma configuração de tronco já tiver sido criada para um tronco específico, esse tronco não será exibido em **Selecionar um Serviço**.
    
    > [!NOTE]
    > Depois de selecionar o escopo da configuração do tronco, não será possível alterá-lo. O campo **Nome** é preenchido previamente com o nome do site ou serviço associado à configuração do tronco e não pode ser alterado. 

5. Especifique um valor **em Máximo de caixas de diálogo insotivas com suporte**. Esse é o número máximo de respostas bifurcadas que um gateway de rede telefônica pública comutado (PSTN), IP-PBX ou Controlador de Borda de Sessão itsp (SBC) pode receber para um INVITE enviado ao Servidor de Mediação. O valor padrão é 20.

    > [!NOTE] 
    > Antes de alterar esse valor, consulte seu provedor de serviços ou fabricante de equipamentos para obter detalhes sobre os recursos do seu sistema. 

6. Selecione uma das seguintes opções de **Nível de suporte de criptografia**:
    - **Obrigatório**: a criptografia SRTP (Secure Real-Time Transport Protocol) deve ser usada para ajudar a proteger o tráfego entre o Servidor de Mediação e o gateway ou PBX (central privada de comutação telefônica).
    - **Opcional**: a criptografia SRTP será usada se o provedor de serviço ou fabricante do equipamento suportá-la.
    - **Sem Suporte**: a criptografia SRTP não é suportada pelo provedor de serviço ou fabricante do equipamento e, portanto, não será usada.
7. Marque a **caixa de seleção Habilitar bypass** de mídia se quiser que a mídia ignore o Servidor de Mediação para processamento pelo ponto de tronco.

    > [!IMPORTANT]
    > Para que o bypass de mídia funcione com êxito, o gateway PSTN, IP-PBX ou Controlador de Borda de Sessão ITSP deve dar suporte a determinados recursos. Para obter detalhes, consulte [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md). 

8. Marque  a caixa de seleção Processamento de mídia centralizado se houver um ponto de término de mídia conhecido (por exemplo, um gateway PSTN em que a terminação de mídia tem o mesmo IP que a terminação de sinalização). Desmarque essa caixa de seleção se o tronco não tiver um ponto de encerramento de mídia conhecido.
9. Se o par de tronco dá suporte ao recebimento de solicitações SIP REFER do Servidor de Mediação, selecione a caixa de seleção Habilitar envio **consultar o gateway.** 

    > [!NOTE] 
    > Se você desabilitar essa opção enquanto **a opção Habilitar desvio** de mídia estiver selecionada, serão necessárias configurações adicionais. Se o par de tronco não dá suporte ao recebimento de solicitações SIP REFER do Servidor de Mediação e o bypass de mídia está habilitado, você também deve executar o cmdlet **Set-CsTrunkConfiguration** para desabilitar o RTCP para chamadas ativas e realizadas, a fim de dar suporte às condições adequadas para bypass de mídia. Como alternativa, você pode selecionar **Habilitar** referência usando o controle de chamada de terceiros se quiser que as chamadas transferidas sejam ignoradas pela mídia e o gateway não dá suporte a solicitações SIP REFER. 

10. (Opcional) Para habilitar o roteamento entre troncos, associe e configure os registros de uso de PSTN a essa configuração de tronco. Os usos PSTN associados a essa configuração de tronco serão aplicados para todas as chamadas de entrada pelo tronco que não são originadas de um ponto de extremidade Skype for Business Server de entrada. Para gerenciar registros de uso de PSTN associados a uma configuração de tronco, use um dos seguintes métodos:
    - Para selecionar um ou mais registros de uma lista de todos os registros de uso PSTN disponíveis em sua implantação Enterprise Voice, clique em **Selecionar**. Destaque os registros que deseja associar a essa configuração de tronco e clique em **OK**.
    - Para remover um registro de uso de PSTN dessa configuração de tronco, selecione-o e clique em **Remover**.
    - Para definir um novo registro de uso de PSTN e associá-lo a essa configuração de tronco, faça o seguinte:
        1. Clique em **Novo**.
        2. No campo **Nome**, especifique um nome descritivo exclusivo para o registro.
            > [!NOTE] 
            > O nome do registro de uso do PSTN deve ser exclusivo dentro de implantação do Enterprise Voice. Após a gravação do registro, o campo **Nome** não pode ser editado. 
        3. Use um dos seguintes métodos para associar e configurar rotas a esse registro de uso de PSTN:
            - Para selecionar uma ou mais rotas na lista de todas as rotas disponíveis em sua implantação Enterprise Voice, clique em **Selecionar**. Destaque as rotas que deseja associar a esse registro de uso de PSTN e clique em **OK**. 
            - Para remover uma rota do registro de uso de PSTN, selecione-a a clique em **Remover**.
            - Para definir uma nova rota e associá-la a essa registro de uso de PSTN, clique em **Novo**. 
            - Para editar uma rota associada a esse registro de uso de PSTN, selecione-a e clique em **Mostrar detalhes**. 
        4. Clique em **OK**.
    - Para editar um registro de uso de PSTN que já está associado a essa configuração de tronco, faça o seguinte:
        1. Selecione o registro de uso de PSTN que deseja editar e clique em **Mostrar detalhes**.
        2. Use um dos seguintes métodos para associar e configurar rotas a esse registro de uso de PSTN:
            - Para selecionar uma ou mais rotas na lista de todas as rotas disponíveis em sua implantação Enterprise Voice, clique em **Selecionar**. Destaque as rotas que deseja associar a esse registro de uso de PSTN e clique em **OK**. 
            - Para remover uma rota do registro de uso de PSTN, selecione-a a clique em **Remover**.
            - Para definir uma nova rota e associá-la a essa registro de uso de PSTN, clique em **Novo**. 
            - Para editar uma rota associada a esse registro de uso de PSTN, selecione-a e clique em **Mostrar detalhes**. 
        3. Clique em **OK**.

    > [!Important]
    > É importante associar registros de uso de PSTN de acordo com o par do Servidor de Mediação associado ao tronco que está sendo configurado. Se o par do Servidor de Mediação for um gateway PSTN ou um Controlador de Borda de Sessão (SBC), é altamente recomendável que a configuração do tronco não esteja associada a um registro de uso PSTN que se encaminhe para um destino PSTN ou qualquer outro sistema downstream conectado por meio de Skype for Business Server. 

11. Organize os registros de uso de PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, selecione esse registro de uso de PSTN e clique nas setas para cima ou para baixo.

    > [!Important]
    > A ordem em que os registros de uso de PSTN são listados na configuração de tronco é importante. Skype for Business Server percorre a lista de cima para baixo. 

12. **Habilitar** a trava RTP deve ser selecionada para habilitar a mídia de bypass para clientes por trás de um NAT (conversão de endereço de rede) ou firewall e um SBC que dá suporte à travamento.
13. **Habilitar o histórico de chamada** de encaminhamento deve ser selecionado para habilitar o envio de informações de histórico de chamada para o ponto de gateway do Servidor de Mediação.
14. Habilitar o encaminhamento de dados **P-Asserted-Identity** deve ser selecionado para habilitar as informações do originador de chamada P-Asserted-Identity (PAI) a serem encaminhadas entre o lado do Servidor de Mediação e o lado do gateway (e vice-versa), quando presente.
15. **Habilitar roteamento de saída do temporizador de failover** deve ser selecionado para habilitar um failover rápido. O gateway associado a esse tronco pode enviar notificações em 10 segundos sobre o processamento de uma chamada de saída. A redirecionação para outro tronco ocorrerá se essa notificação não for recebida pelo Servidor de Mediação. Em redes nas quais a latência pode atrasar o tempo de resposta em mais de 10 segundos, o failover rápido deve ser desabilitado.
16. (Opcional) Associe e configure **regras de conversão de número de chamada** ao tronco. Essas regras de conversão se aplicam ao número de chamada para chamadas de saída.
    - Para escolher uma ou mais regras em uma lista de todas as regras de conversão disponíveis em sua implantação Enterprise Voice, clique em **Selecionar**. Em **Selecionar Regras de Conversão**, clique nas regras que deseja associar ao tronco e clique em **OK**.
    - Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**. Para obter detalhes sobre como definir uma nova regra, consulte [Defining translation rules in Skype for Business Server](defining-translation-rules.md).
    - Para editar uma regra de conversão que já está associada ao tronco, clique no nome da regra e, depois, em **Mostrar detalhes**. Para obter detalhes, consulte [Defining translation rules in Skype for Business Server](defining-translation-rules.md).
    - Para copiar uma regra de conversão existente a fim de usá-la como ponto de partida para definir uma nova regra, clique no nome da regra, em seguida, em **Copiar** e, então, clique em **Colar**. Para obter detalhes, consulte [Defining translation rules in Skype for Business Server](defining-translation-rules.md).
    - Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em **Remover**.
    > [!Warning]
    > Não associe regras de conversão a um tronco se você tiver configurado as regras de conversão no ponto de tronco associado, pois as duas regras podem entrar em conflito. 

17. (Opcional) Associe e configure **regras de conversão de número chamado** ao tronco. As regras de conversão se aplicam ao número chamado de uma chamada de saída.
    - Para escolher uma ou mais regras em uma lista de todas as regras de conversão disponíveis em sua implantação Enterprise Voice, clique em **Selecionar**. Em **Selecionar Regras de Conversão**, clique nas regras que deseja associar ao tronco e clique em **OK**.
    - Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**. Para obter detalhes sobre como definir uma nova regra, consulte [Defining translation rules in Skype for Business Server](defining-translation-rules.md).
    - Para editar uma regra de conversão que já está associada ao tronco, clique no nome da regra e, depois, em **Mostrar detalhes**. Para obter detalhes, consulte [Defining translation rules in Skype for Business Server](defining-translation-rules.md).
    - Para copiar uma regra de conversão existente a fim de usá-la como ponto de partida para definir uma nova regra, clique no nome da regra, em seguida, em **Copiar** e, então, clique em **Colar**. Para obter detalhes, consulte [Defining translation rules in Skype for Business Server](defining-translation-rules.md).
    - Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em **Remover**.

    > [!Warning] 
    > Não associe regras de conversão a um tronco se você tiver configurado as regras de conversão no ponto de tronco associado, pois as duas regras podem entrar em conflito. 

18. Certifique-se de que as regras de conversão do tronco sejam organizadas na ordem correta. Para alterar a posição de uma regra na lista, realce o nome da regra e clique na seta para cima ou para baixo.

    >[!Important] 
    > Skype for Business Server percorre a lista de regras de conversão da parte superior para baixo e usa a primeira regra que corresponde ao número discado. Se você configurar um tronco de modo que um número discado possa corresponder a mais de uma regra de conversão, certifique-se de que as regras mais restritivas estejam classificadas acima das regras menos restritivas. Por exemplo, se tiver incluído uma regra de conversão que corresponda a qualquer número de 11 dígitos e uma regra de conversão que corresponda somente a números de 11 dígitos que comecem com +1425, certifique-se de que a regra que corresponde a qualquer número de 11 dígitos esteja classificada *abaixo* da regra mais restritiva. 

19. Depois de concluir a configuração do tronco, clique em **OK**.
20. Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**. 

    > [!Note]
    > Sempre que você criar ou modificar uma configuração de tronco, execute o comando **Confirmar tudo** para publicar a alteração da configuração. Para obter detalhes, [consulte Publicar alterações pendentes na configuração de roteamento de voz](/previous-versions/office/lync-server-2013/lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration). (PRECISA DE NOVO LINK?)

Depois de configurar o tronco, continue configurando o bypass de mídia escolhendo entre as opções globais de bypass de mídia, conforme descrito em [Deploy media bypass in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-media-bypass.md).
