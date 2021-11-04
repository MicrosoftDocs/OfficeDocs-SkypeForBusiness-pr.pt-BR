---
title: Skype for Business Server - Configurar um tronco sem bypass de mídia
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
description: 'Como configurar um tronco com bypass de mídia habilitado. '
ms.openlocfilehash: 906e5d793ba9b671d9a3d19b144ceac89b74428b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60751730"
---
# <a name="skype-for-business-server---configure-a-trunk-without-media-bypass"></a>Skype for Business Server - Configurar um tronco sem bypass de mídia

Se quiser configurar um tronco com desvio de mídia desabilitado, siga estas etapas. Se você quiser configurar um tronco com bypass de mídia habilitado, consulte [Configure a trunk with media bypass in Skype for Business Server](configure-a-trunk-with-media-bypass.md).

Uma configuração de tronco, como descrito abaixo, agrupa um conjunto de parâmetros que são aplicados a troncos designados com essa configuração. Uma determinada configuração de tronco pode ter o escopo de forma global (a todos os troncos que não têm uma configuração de site ou pool mais específica), para um site ou para um pool. A configuração de tronco no nível do pool é usada para definir o escopo de uma configuração específica de um tronco individual.

**Para configurar um tronco sem bypass de mídia**

1. Abra Skype painel de controle do servidor busines.
3. Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em **Configuração de Tronco**.
4. Na página **Configuração de Tronco**, use um dos seguintes métodos para configurar um tronco:
    - Clique duas vezes em um tronco existente (por exemplo, o tronco **Global**) para exibir a caixa de diálogo **Editar Configuração de Tronco**.
    - Clique em **Novo** e selecione um escopo para a nova configuração do tronco:
        - **Tronco do** site : escolha o site para essa configuração de tronco **em Selecionar um Site** e clique em **OK**. Observe que se uma configuração de tronco já tiver sido criada para um site, o site não aparecerá em **Selecionar um Site**. Essa configuração de tronco será aplicada a todos os troncos do site.
        - **Tronco do pool**: escolha um nome para o tronco ao qual essa configuração de tronco se aplica em **Selecionar um Serviço** e clique em **OK**. Esse tronco pode ser o tronco raiz ou quaisquer troncos adicionais definidos no Construtor de Topologias. Observe que se uma configuração de tronco já tiver sido criada para um tronco específico, esse tronco não será exibido em **Selecionar um Serviço**.
    > [!Note] 
    > Depois de selecionar o escopo da configuração do tronco, não será possível alterá-lo. O campo **Nome** é preenchido previamente com o nome do site ou serviço associado à configuração do tronco e não pode ser alterado. 

5. Selecione uma das seguintes opções de **Nível de suporte de criptografia**:
    - **Obrigatório**: a criptografia SRTP (Secure Real-Time Transport Protocol) deve ser usada para ajudar a proteger o tráfego entre o Servidor de Mediação e o gateway ou PBX (central privada de comutação telefônica).
    - **Opcional**: a criptografia SRTP será usada se o provedor de serviço ou fabricante do equipamento suportá-la.
    - **Sem Suporte**: a criptografia SRTP não é suportada pelo provedor de serviço ou fabricante do equipamento e, portanto, não será usada.
6. Certifique-se de que a caixa de seleção **Habilitar bypass de mídia** esteja desmarcada.
7. Marque a caixa de seleção **Processamento de mídia centralizado** se houver um ponto de encerramento de mídia conhecido [por exemplo, um gateway PSTN (Rede Telefônica Pública Comutada) no qual o encerramento de mídia tenha o mesmo IP que o encerramento de sinalização]. Desmarque essa caixa de seleção se o tronco não tiver um ponto de encerramento de mídia conhecido.
8. Se o par de tronco dá suporte ao recebimento de solicitações SIP REFER do Servidor de Mediação, selecione a caixa de seleção Habilitar envio **consultar o gateway.**
9. (Opcional) Para habilitar o roteamento entre troncos, associe e configure os registros de uso de PSTN a essa configuração de tronco. Os usos PSTN associados a essa configuração de tronco serão aplicados para todas as chamadas de entrada pelo tronco que não são originadas de um ponto de extremidade Skype for Business Server de entrada. Para gerenciar registros de uso de PSTN associados a uma configuração de tronco, use um dos seguintes métodos:
    - Para selecionar um ou mais registros de uma lista de todos os registros de uso PSTN disponíveis em sua implantação Enterprise Voice, clique em **Selecionar**. Destaque os registros que deseja associar a essa configuração de tronco e clique em **OK**.
    - Para remover um registro de uso de PSTN dessa configuração de tronco, selecione-o e clique em **Remover**.
    - Para definir um novo registro de uso de PSTN e associá-lo a essa configuração de tronco, faça o seguinte:
        1. Clique em **Novo**.
        2. No campo **Nome**, especifique um nome descritivo exclusivo para o registro.
            > [!Note] 
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

10. Organize os registros de uso de PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, selecione esse registro de uso de PSTN e clique nas setas para cima ou para baixo.
    > [!Important] 
    > A ordem em que os registros de uso de PSTN são listados na configuração de tronco é importante. Skype for Business Server percorre a lista de cima para baixo. 

11. **Habilitar engatador RTP** deve ser selecionado para habilitar bypass de mídia para clientes sob um NAT ou firewall e um SBC que dê suporte ao engatador.
12. **Habilitar o histórico de chamada** de encaminhamento deve ser selecionado para habilitar o envio de informações de histórico de chamada para o ponto de gateway do Servidor de Mediação.
13. Habilitar o encaminhamento de dados **P-Asserted-Identity** deve ser selecionado para permitir que as informações do originador de chamada pai sejam encaminhadas entre o lado do Servidor de Mediação e o lado do gateway (e vice-versa), quando presente.
14. **Habilitar roteamento de saída do temporizador de failover** deve ser selecionado para habilitar um failover rápido. O gateway associado a esse tronco pode enviar notificações em 10 segundos sobre o processamento de uma chamada de saída. A redirecionação para outro tronco ocorrerá se essa notificação não for recebida pelo Servidor de Mediação. Em redes nas quais a latência pode atrasar o tempo de resposta em mais de 10 segundos, o failover rápido deve ser desabilitado.
15. (Opcional) Associe **e configure regras de conversão de** número de chamada para o tronco. Essas regras de conversão se aplicam ao número de chamada para chamadas de saída.
    - Para escolher uma ou mais regras em uma lista de todas as regras de conversão disponíveis em sua implantação Enterprise Voice, clique em **Selecionar**. Em **Selecionar Regras de Conversão**, clique nas regras que deseja associar ao tronco e clique em **OK**.
    - Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**. Para obter detalhes sobre como definir uma nova regra, consulte [Defining translation rules in Skype for Business Server](defining-translation-rules.md).
    - Para editar uma regra de conversão que já está associada ao tronco, clique no nome da regra e, depois, em **Mostrar detalhes**. Para obter detalhes, consulte [Defining translation rules in Skype for Business Server](defining-translation-rules.md).
    - Para copiar uma regra de conversão existente a fim de usá-la como ponto de partida para definir uma nova regra, clique no nome da regra, em seguida, em **Copiar** e, então, clique em **Colar**. Para obter detalhes, consulte [Defining translation rules in Skype for Business Server](defining-translation-rules.md).
    - Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em **Remover**.

    > [!Warning]
    > Não associe regras de conversão a um tronco se você tiver configurado as regras de conversão no ponto de tronco associado, pois as duas regras podem entrar em conflito. 

16. (Opcional) Associe e configure **regras de conversão de número chamado** ao tronco. As regras de conversão se aplicam ao número chamado de uma chamada de saída.
    - Para escolher uma ou mais regras em uma lista de todas as regras de conversão disponíveis em sua implantação Enterprise Voice, clique em **Selecionar**. Em Selecionar Regras de Tradução, clique nas regras que você deseja associar ao tronco e clique em **OK**.
    - Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**. Para obter detalhes sobre como definir uma nova regra, consulte [Defining translation rules in Skype for Business Server](defining-translation-rules.md).
    - Para editar uma regra de conversão que já está associada ao tronco, clique no nome da regra e, depois, em **Mostrar detalhes**. Para obter detalhes, consulte [Defining translation rules in Skype for Business Server](defining-translation-rules.md).
    - Para copiar uma regra de conversão existente a fim de usá-la como ponto de partida para definir uma nova regra, clique no nome da regra, em seguida, em **Copiar** e, então, clique em **Colar**. Para obter detalhes, consulte [Defining translation rules in Skype for Business Server](defining-translation-rules.md).
    - Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em **Remover**.

    > [!Caution] 
    > Não associe regras de conversão a um tronco se você tiver configurado as regras de conversão no ponto de tronco associado, pois as duas regras podem entrar em conflito. 

17. Certifique-se de que as regras de conversão do tronco sejam organizadas na ordem correta. Para alterar a posição de uma regra na lista, destaque o nome da regra e clique na seta para cima ou para baixo.

    > [!Important] 
    > Skype for Business Server percorre a lista de regras de conversão da parte superior para baixo e usa a primeira regra que corresponde ao número discado. Se você configurar um tronco de modo que um número discado possa corresponder a mais de uma regra de conversão, certifique-se de que as regras mais restritivas estejam classificadas acima das regras menos restritivas. Por exemplo, se tiver incluído uma regra de conversão que corresponda a qualquer número de 11 dígitos e uma regra de conversão que corresponda somente a números de 11 dígitos que comecem com +1425, certifique-se de que a regra que corresponde a qualquer número de 11 dígitos esteja classificada abaixo da regra mais restritiva. 

18. Depois de concluir a configuração do tronco, clique em **OK**.
19. Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**. 

    > [!Note]
    > Sempre que você criar ou modificar uma configuração de tronco, execute o comando **Confirmar tudo** para publicar a alteração da configuração. Para obter detalhes, consulte Publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013 na documentação Operações. 
