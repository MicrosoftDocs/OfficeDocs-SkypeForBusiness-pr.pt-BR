---
title: Configurar um tronco com bypass de mídia no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Siga estas etapas para configurar um tronco com bypass de mídia habilitado. '
ms.openlocfilehash: 293c39884c1ef6c8e82521b3fd248ae6bbc18d05
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009544"
---
# <a name="configure-a-trunk-with-media-bypass-in-skype-for-business-server"></a>Configurar um tronco com bypass de mídia no Skype for Business Server

Siga estas etapas para configurar um tronco com bypass de mídia habilitado. Para configurar um tronco com bypass de mídia desabilitado, confira [configurar um tronco sem bypass de mídia no Skype for Business Server](configure-a-trunk-without-media-bypass.md). O bypass de mídia é útil quando você deseja minimizar o número de Servidores de Mediação implantados. Geralmente, um pool de Servidores de Mediação será implantado em um site central e controlará os gateways em sites locais. Habilitar o bypass de mídia permite que a mídia para chamadas PSTN de clientes em sites locais flua diretamente pelos gateways para estes sites. Os roteamentos de chamada de saída do Skype for Business Server e as políticas do Enterprise Voice devem ser configurados corretamente para que as chamadas PSTN de clientes em um site de filial sejam roteadas para o gateway apropriado.

É altamente recomendável que você habilite o bypass de mídia. No entanto, antes de habilitar o bypass de mídia em um tronco SIP, confirme se o seu provedor de tronco SIP qualificado suporta bypass de mídia e é capaz de acomodar os requisitos para habilitar o cenário com êxito. Especificamente, o provedor deve ter os endereços IP de servidores na rede interna da sua organização. Se o provedor não oferecer suporte a esse cenário, o bypass de mídia não terá êxito. Para obter detalhes, consulte [Plan for Media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

> [!NOTE]
> O bypass de mídia não interoperará com cada gateway PSTN (rede telefônica pública comutada), IP-PBX e SBC (controlador de borda de sessão). A Microsoft testou um conjunto de gateways PSTN e SBCs com parceiros certificados e realizou alguns testes com IP-PBXs da Cisco. O bypass de mídia é suportado apenas com produtos e versões listados na página [infraestrutura de telefonia para o Skype for Business Server](../../../SfbPartnerCertification/certification/infra-gateways.md) . 


Uma configuração de tronco, conforme descrito abaixo, agrupa um conjunto de parâmetros que são aplicados a troncos atribuídos a essa configuração de tronco. Uma determinada configuração de tronco pode ter o escopo de forma global (a todos os troncos que não têm uma configuração de site ou pool mais específica), para um site ou para um pool. A configuração de tronco no nível do pool é usada para definir o escopo de uma configuração específica de um tronco individual.

**Para configurar um tronco com bypass de mídia**

1. Abra o painel de controle do Skype for stress Server.
2. Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em **Configuração de Tronco**.
3. Na página **Configuração de Tronco**, use um dos seguintes métodos para configurar um tronco:
    - Clique duas vezes em um tronco existente (por exemplo, o tronco **Global**) para exibir a caixa de diálogo **Editar Configuração de Tronco**.
    - Clique em **Novo** e selecione um escopo para a nova configuração do tronco:
        - **Tronco de site**: escolha o site para esta configuração de tronco em **selecionar um site**e clique em **OK**. Observe que se uma configuração de tronco já tiver sido criada para um site, o site não aparecerá em **Selecionar um Site**. Essa configuração de tronco será aplicada a todos os troncos do site.
        - **Tronco do pool**: escolha o nome do tronco ao qual essa configuração de tronco se aplica. Esse tronco pode ser o tronco raiz ou qualquer tronco adicional definido no construtor de topologias. Em **selecionar um serviço**, clique em **OK**. Observe que se uma configuração de tronco já tiver sido criada para um tronco específico, esse tronco não será exibido em **Selecionar um Serviço**.
    
    > [!NOTE]
    > Depois de selecionar o escopo da configuração do tronco, não será possível alterá-lo. O campo **Nome** é preenchido previamente com o nome do site ou serviço associado à configuração do tronco e não pode ser alterado. 

5. Especifique um valor no **máximo de caixas de diálogo iniciais com suporte**. Este é o número máximo de respostas bifurcadas que um gateway PSTN (rede telefônica pública comutada), IP-PBX ou ITSP de borda de sessão (SBC) pode receber um convite enviado para o servidor de mediação. O valor padrão é 20.

    > [!NOTE] 
    > Antes de alterar esse valor, consulte seu provedor de serviços ou fabricante do equipamento para obter detalhes sobre os recursos do seu sistema. 

6. Selecione uma das seguintes opções de **Nível de suporte de criptografia**:
    - **Obrigatório**: a criptografia SRTP (Secure Real-Time Transport Protocol) deve ser usada para ajudar a proteger o tráfego entre o Servidor de Mediação e o gateway ou PBX (central privada de comutação telefônica).
    - **Opcional**: a criptografia SRTP será usada se o provedor de serviço ou fabricante do equipamento suportá-la.
    - **Sem Suporte**: a criptografia SRTP não é suportada pelo provedor de serviço ou fabricante do equipamento e, portanto, não será usada.
7. Marque a caixa de seleção **habilitar bypass de mídia** se quiser que a mídia ignore o servidor de mediação para processamento pelo par de troncos.

    > [!IMPORTANT]
    > Para que o bypass de mídia funcione com êxito, o gateway PSTN, IP-PBX ou controlador de borda da sessão ITSP deve suportar determinados recursos. Para obter detalhes, consulte [Plan for Media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md). 

8. Marque a caixa de seleção **processamento de mídia centralizado** se houver um ponto de terminação de mídia conhecido (por exemplo, um gateway PSTN onde a terminação de mídia tem o mesmo IP que a terminação de sinalização). Desmarque essa caixa de seleção se o tronco não tiver um ponto de encerramento de mídia conhecido.
9. Se o par de troncos suportar o recebimento de solicitações SIP REFEREntes ao servidor de mediação, marque a caixa de seleção **habilitar o envio se refere ao gateway** . 

    > [!NOTE] 
    > Se você desabilitar essa opção enquanto a opção **habilitar bypass de mídia** estiver selecionada, configurações adicionais serão necessárias. Se o par de troncos não oferecer suporte ao recebimento de solicitações SIP de referência do servidor de mediação e o bypass de mídia estiver habilitado, você também deverá executar o cmdlet **set-CsTrunkConfiguration** para desabilitar o RTCP para chamadas ativas e mantidas a fim de oferecer suporte às condições adequadas para o bypass de mídia. Como alternativa, você pode selecionar **habilitar fazer referência usando o controle de chamada de terceiros** se quiser que as chamadas transferidas sejam ignoradas, e o gateway não oferece suporte a solicitações de referência SIP. 

10. (Opcional) Para habilitar o roteamento entre troncos, associe e configure os registros de uso de PSTN a essa configuração de tronco. Os usos de PSTN associados a essa configuração de tronco serão aplicados a todas as chamadas de entrada através do tronco que não é proveniente de um ponto de extremidade do Skype for Business Server. Para gerenciar registros de uso de PSTN associados a uma configuração de tronco, use um dos seguintes métodos:
    - Para selecionar um ou mais registros de uma lista de todos os registros de uso de PSTN disponíveis em sua implantação do Enterprise Voice, clique em **selecionar**. Destaque os registros que deseja associar a essa configuração de tronco e clique em **OK**.
    - Para remover um registro de uso de PSTN dessa configuração de tronco, selecione-o e clique em **Remover**.
    - Para definir um novo registro de uso de PSTN e associá-lo a essa configuração de tronco, faça o seguinte:
        1. Clique em **Novo**.
        2. No campo **Nome**, especifique um nome descritivo exclusivo para o registro.
            > [!NOTE] 
            > O nome do registro de uso do PSTN deve ser exclusivo dentro de implantação do Enterprise Voice. Após a gravação do registro, o campo **Nome** não pode ser editado. 
        3. Use um dos seguintes métodos para associar e configurar rotas a esse registro de uso de PSTN:
            - Para selecionar uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **selecionar**. Destaque as rotas que deseja associar a esse registro de uso de PSTN e clique em **OK**. 
            - Para remover uma rota do registro de uso de PSTN, selecione-a a clique em **Remover**.
            - Para definir uma nova rota e associá-la a essa registro de uso de PSTN, clique em **Novo**. 
            - Para editar uma rota associada a esse registro de uso de PSTN, selecione-a e clique em **Mostrar detalhes**. 
        4. Clique em **OK**.
    - Para editar um registro de uso de PSTN que já está associado a essa configuração de tronco, faça o seguinte:
        1. Selecione o registro de uso de PSTN que deseja editar e clique em **Mostrar detalhes**.
        2. Use um dos seguintes métodos para associar e configurar rotas a esse registro de uso de PSTN:
            - Para selecionar uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **selecionar**. Destaque as rotas que deseja associar a esse registro de uso de PSTN e clique em **OK**. 
            - Para remover uma rota do registro de uso de PSTN, selecione-a a clique em **Remover**.
            - Para definir uma nova rota e associá-la a essa registro de uso de PSTN, clique em **Novo**. 
            - Para editar uma rota associada a esse registro de uso de PSTN, selecione-a e clique em **Mostrar detalhes**. 
        3. Clique em **OK**.

    > [!Important]
    > É importante associar registros de uso de PSTN de acordo com o ponto do servidor de mediação associado ao tronco que está sendo configurado. Se o ponto de servidor de mediação for um gateway PSTN ou um SBC (controlador de borda de sessão), é altamente recomendável que a configuração de tronco não esteja associada a um registro de uso de PSTN que roteia para um destino PSTN ou qualquer outro sistema downstream conectado via Skype para Business Server. 

11. Organize os registros de uso de PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, selecione esse registro de uso de PSTN e clique nas setas para cima ou para baixo.

    > [!Important]
    > A ordem em que os registros de uso de PSTN são listados na configuração de tronco é importante. O Skype for Business Server atravessa a lista de cima para baixo. 

12. **Habilitar a trava de RTP** deve ser selecionada para habilitar o bypass de mídia para clientes por trás de uma NAT (conversão de endereço de rede) ou firewall e um SBC que dê suporte ao engatador.
13. **Habilitar o histórico de chamadas de encaminhamento** deve ser selecionado para habilitar o envio de informações de histórico de chamadas para o par de gateway do servidor de mediação.
14. **Habilitar os dados de encaminhamento p-Asserted-Identity** devem ser selecionados para permitir que as informações de originador de chamada p-assertd-Identity (pai) sejam encaminhadas entre o lado do servidor de mediação e o lado do gateway (e vice-versa), quando presentes.
15. **Habilitar roteamento de saída do temporizador de failover** deve ser selecionado para habilitar um failover rápido. O gateway associado a esse tronco pode enviar notificações em 10 segundos sobre o processamento de uma chamada de saída. O redirecionamento para outro tronco ocorrerá se essa notificação não for recebida pelo servidor de mediação. Em redes nas quais a latência pode atrasar o tempo de resposta em mais de 10 segundos, o failover rápido deve ser desabilitado.
16. (Opcional) Associe e configure **regras de conversão de número de chamada** ao tronco. Essas regras de conversão se aplicam ao número de chamada para chamadas de saída.
    - Para escolher uma ou mais regras de uma lista de todas as regras de conversão que estão disponíveis em sua implantação do Enterprise Voice, clique em **selecionar**. Em **Selecionar Regras de Conversão**, clique nas regras que deseja associar ao tronco e clique em **OK**.
    - Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**. Para obter detalhes sobre como definir uma nova regra, consulte [definindo regras de conversão no Skype for Business Server](defining-translation-rules.md).
    - Para editar uma regra de conversão que já está associada ao tronco, clique no nome da regra e, depois, em **Mostrar detalhes**. Para obter detalhes, consulte [definindo regras de conversão no Skype for Business Server](defining-translation-rules.md).
    - Para copiar uma regra de conversão existente a fim de usá-la como ponto de partida para definir uma nova regra, clique no nome da regra, em seguida, em **Copiar** e, então, clique em **Colar**. Para obter detalhes, consulte [definindo regras de conversão no Skype for Business Server](defining-translation-rules.md).
    - Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em **Remover **.
    > [!Warning]
    > Não associe regras de conversão a um tronco se você tiver configurado as regras de conversão no ponto de tronco associado, pois as duas regras podem entrar em conflito. 

17. (Opcional) Associe e configure **regras de conversão de número chamado** ao tronco. As regras de conversão se aplicam ao número chamado de uma chamada de saída.
    - Para escolher uma ou mais regras de uma lista de todas as regras de conversão que estão disponíveis em sua implantação do Enterprise Voice, clique em **selecionar**. Em **Selecionar Regras de Conversão**, clique nas regras que deseja associar ao tronco e clique em **OK**.
    - Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**. Para obter detalhes sobre como definir uma nova regra, consulte [definindo regras de conversão no Skype for Business Server](defining-translation-rules.md).
    - Para editar uma regra de conversão que já está associada ao tronco, clique no nome da regra e, depois, em **Mostrar detalhes**. Para obter detalhes, consulte [definindo regras de conversão no Skype for Business Server](defining-translation-rules.md).
    - Para copiar uma regra de conversão existente a fim de usá-la como ponto de partida para definir uma nova regra, clique no nome da regra, em seguida, em **Copiar** e, então, clique em **Colar**. Para obter detalhes, consulte [definindo regras de conversão no Skype for Business Server](defining-translation-rules.md).
    - Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em **Remover **.

    > [!Warning] 
    > Não associe regras de conversão a um tronco se você tiver configurado as regras de conversão no ponto de tronco associado, pois as duas regras podem entrar em conflito. 

18. Certifique-se de que as regras de conversão do tronco estejam organizadas na ordem correta. Para alterar a posição de uma regra na lista, realce o nome da regra e clique na seta para cima ou para baixo.

    >[!Important] 
    > O Skype for Business Server atravessa a lista de regras de conversão de cima para baixo e usa a primeira regra que corresponde ao número discado. Se você configurar um tronco de modo que um número discado possa corresponder a mais de uma regra de conversão, certifique-se de que as regras mais restritivas estejam classificadas acima das regras menos restritivas. Por exemplo, se tiver incluído uma regra de conversão que corresponda a qualquer número de 11 dígitos e uma regra de conversão que corresponda somente a números de 11 dígitos que comecem com +1425, certifique-se de que a regra que corresponde a qualquer número de 11 dígitos esteja classificada *abaixo* da regra mais restritiva. 

19. Depois de concluir a configuração do tronco, clique em **OK**.
20. Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**. 

    > [!Note]
    > Sempre que você criar ou modificar uma configuração de tronco, execute o comando **Confirmar tudo** para publicar a alteração da configuração. Para obter detalhes, consulte [Publish Pending Changes to The Voice Routing Configuration](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx). (PRECISA DE UM NOVO LINK?)

Depois de configurar o tronco, continue Configurando o bypass de mídia escolhendo entre as opções de bypass de mídia global, conforme descrito em [Deploy Media bypass in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-media-bypass.md).

