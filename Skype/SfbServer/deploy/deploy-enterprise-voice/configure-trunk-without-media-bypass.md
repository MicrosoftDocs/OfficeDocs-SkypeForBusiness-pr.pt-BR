---
title: 'Skype for Business Server: configurar um tronco sem bypass de mídia'
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
description: 'Resumo: Configure um tronco sem bypass de mídia habilitado para Skype for Business Server.'
ms.openlocfilehash: 09d178cf2deeb27ec47c39090f7dcc233af3cbb0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759113"
---
# <a name="skype-for-business-server-configure-a-trunk-without-media-bypass"></a>Skype for Business Server: configurar um tronco sem bypass de mídia

**Resumo:** Configure um tronco sem bypass de mídia habilitado para Skype for Business Server.

Se quiser configurar um tronco com desvio de mídia desabilitado, siga estas etapas. Se você quiser configurar um tronco com bypass de mídia habilitado, consulte [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md).

Uma configuração de tronco, como descrito abaixo, agrupa um conjunto de parâmetros que são aplicados a troncos designados com essa configuração. Uma determinada configuração de tronco pode ter o escopo de forma global (a todos os troncos que não têm uma configuração de site ou pool mais específica), para um site ou para um pool. A configuração de tronco no nível do pool é usada para definir o escopo de uma configuração específica de um tronco individual.

### <a name="to-configure-a-trunk-without-media-bypass"></a>Para configurar um tronco sem bypass de mídia

1. Abra Skype for Business Server Painel de Controle.

2. Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em **Configuração de Tronco**.

3. Na página **Configuração de Tronco**, use um dos seguintes métodos para configurar um tronco:

   - Clique duas vezes em um tronco existente (por exemplo, o tronco **Global**) para exibir a caixa de diálogo **Editar Configuração de Tronco**.

   - Clique em **Novo** e selecione um escopo para a nova configuração do tronco:

   - **Tronco do** site : escolha o site para essa configuração de tronco **em Selecionar um Site** e clique em **OK**. Observe que se uma configuração de tronco já tiver sido criada para um site, o site não aparecerá em **Selecionar um Site**. Essa configuração de tronco será aplicada a todos os troncos do site.

   - **Tronco do pool**: escolha um nome para o tronco ao qual essa configuração de tronco se aplica em **Selecionar um Serviço** e clique em **OK**. Esse tronco pode ser o tronco raiz ou quaisquer troncos adicionais definidos no Construtor de Topologias. Observe que se uma configuração de tronco já tiver sido criada para um tronco específico, esse tronco não será exibido em **Selecionar um Serviço**.

     > [!NOTE]
     > Depois de selecionar o escopo da configuração do tronco, não será possível alterá-lo. > O **campo Nome** é pré-preenchido com o nome do site ou serviço associado da configuração do tronco e não pode ser alterado.

4. Selecione uma das seguintes opções de **Nível de suporte de criptografia**:

   - **Obrigatório:** a criptografia SRTP (Protocolo de Transporte em Tempo Real Seguro) deve ser usada para ajudar a proteger o tráfego entre o Servidor de Mediação e o gateway ou o PBX (Private Branch eXchange).

   - **Opcional**: a criptografia SRTP será usada se o provedor de serviço ou fabricante do equipamento suportá-la.

   - **Sem Suporte**: a criptografia SRTP não é suportada pelo provedor de serviço ou fabricante do equipamento e, portanto, não será usada.

5. Certifique-se de que a caixa de seleção **Habilitar bypass de mídia** esteja desmarcada.

6. Marque  a caixa de seleção Processamento de mídia centralizado se houver um ponto de terminação de mídia conhecido (por exemplo, um gateway PSTN (Rede Telefônica Pública Comutado) onde a terminação de mídia tem o mesmo IP da terminação de sinalização). Desmarque essa caixa de seleção se o tronco não tiver um ponto de encerramento de mídia conhecido.

7. Se o par de tronco dá suporte ao recebimento de solicitações SIP REFER do Servidor de Mediação, selecione a caixa de seleção Habilitar envio **consultar o gateway.**

8. (Opcional) Para habilitar o roteamento entre troncos, associe e configure os registros de uso de PSTN a essa configuração de tronco. Os usos PSTN associados a essa configuração de tronco serão aplicados para todas as chamadas de entrada pelo tronco que não são originadas de um ponto de extremidade Skype for Business Server de entrada. Para gerenciar registros de uso de PSTN associados a uma configuração de tronco, use um dos seguintes métodos:

   - Para selecionar um ou mais registros de uma lista de todos os registros de uso PSTN disponíveis em sua implantação Enterprise Voice, clique em **Selecionar**. Destaque os registros que deseja associar a essa configuração de tronco e clique em **OK**.

   - Para remover um registro de uso de PSTN dessa configuração de tronco, selecione-o e clique em **Remover**.

   - Para definir um novo registro de uso de PSTN e associá-lo a essa configuração de tronco, faça o seguinte:

     a. Clique em **Novo**.

     b. No campo **Nome**, especifique um nome descritivo exclusivo para o registro.

     > [!NOTE]
     > O nome do registro de uso do PSTN deve ser exclusivo dentro de implantação do Enterprise Voice. Após a gravação do registro, o campo **Nome** não pode ser editado.

     c. Use um dos seguintes métodos para associar e configurar rotas a esse registro de uso de PSTN:

     - Para selecionar uma ou mais rotas na lista de todas as rotas disponíveis em sua implantação Enterprise Voice, clique em **Selecionar**. Destaque as rotas que deseja associar a esse registro de uso de PSTN e clique em **OK**.

     - Para remover uma rota do registro de uso de PSTN, selecione-a a clique em **Remover**.

     - Para definir uma nova rota e associá-la a essa registro de uso de PSTN, clique em **Novo**. Para obter detalhes, [consulte Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).

     - Para editar uma rota associada a esse registro de uso de PSTN, selecione-a e clique em **Mostrar detalhes**.

     d. Clique em **OK**.

   - Para editar um registro de uso de PSTN que já está associado a essa configuração de tronco, faça o seguinte:

     a. Selecione o registro de uso de PSTN que deseja editar e clique em **Mostrar detalhes**.

     b. Use um dos seguintes métodos para associar e configurar rotas a esse registro de uso de PSTN:

     - Para selecionar uma ou mais rotas na lista de todas as rotas disponíveis em sua implantação Enterprise Voice, clique em **Selecionar**. Destaque as rotas que deseja associar a esse registro de uso de PSTN e clique em **OK**.

     - Para remover uma rota do registro de uso de PSTN, selecione-a a clique em **Remover**.

     - Para definir uma nova rota e associá-la a essa registro de uso de PSTN, clique em **Novo**. Para obter detalhes, [consulte Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).

     - Para editar uma rota associada a esse registro de uso de PSTN, selecione-a e clique em **Mostrar detalhes**.

     c. Clique em **OK**.

     > [!IMPORTANT]
     > É importante associar registros de uso de PSTN de acordo com o par do Servidor de Mediação associado ao tronco que está sendo configurado. Se o par do Servidor de Mediação for um gateway PSTN ou um Controlador de Borda de Sessão (SBC), é altamente recomendável que a configuração do tronco não esteja associada a um registro de uso PSTN que se encaminhe para um destino PSTN ou qualquer outro sistema downstream conectado por meio de Skype for Business Server.

9. Organize os registros de uso do PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, selecione o registro de uso PSTN e clique nas setas para cima ou para baixo.

    > [!IMPORTANT]
    > A ordem em que os registros de uso de PSTN são listados na configuração de tronco é importante. Skype for Business Server percorre a lista de cima para baixo.

10. **Habilitar engatador RTP** deve ser selecionado para habilitar bypass de mídia para clientes sob um NAT ou firewall e um SBC que dê suporte ao engatador.

11. **Habilitar o histórico de chamada** de encaminhamento deve ser selecionado para habilitar o envio de informações de histórico de chamada para o ponto de gateway do Servidor de Mediação.

12. Habilitar o encaminhamento de dados **P-Asserted-Identity** deve ser selecionado para permitir que as informações do originador de chamada pai sejam encaminhadas entre o lado do Servidor de Mediação e o lado do gateway (e vice-versa), quando presente.

13. **Habilitar roteamento de saída do temporizador de failover** deve ser selecionado para habilitar um failover rápido. O gateway associado a esse tronco pode enviar notificações em 10 segundos sobre o processamento de uma chamada de saída. A redirecionação para outro tronco ocorrerá se essa notificação não for recebida pelo Servidor de Mediação. Em redes nas quais a latência pode atrasar o tempo de resposta em mais de 10 segundos, o failover rápido deve ser desabilitado.

14. (Opcional) Associe e configure **regras de conversão de número de chamada** ao tronco. Essas regras de conversão se aplicam ao número de chamada das chamadas de saída.

    - Para escolher uma ou mais regras em uma lista de todas as regras de conversão disponíveis em sua implantação Enterprise Voice, clique em **Selecionar**. Em **Selecionar Regras de Conversão**, clique nas regras que deseja associar ao tronco e clique em **OK**.

    - Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**. Para obter detalhes sobre regras de conversão, consulte [Regras de conversão em Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).

    - Para editar uma regra de conversão que já está associada ao tronco, clique no nome da regra e, depois, em **Mostrar detalhes**.

    - Para copiar uma regra de conversão existente a fim de usá-la como ponto de partida para definir uma nova regra, clique no nome da regra, em seguida, em **Copiar** e, então, clique em **Colar**.

    - Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em **Remover**.

      > [!CAUTION]
      > Não associe regras de conversão a um tronco se você tiver configurado as regras de conversão no ponto de tronco associado, pois as duas regras podem entrar em conflito.

15. (Opcional) Associe e configure **regras de conversão de número chamado** ao tronco. As regras de conversão se aplicam ao número chamado de uma chamada de saída.

    - Para escolher uma ou mais regras em uma lista de todas as regras de conversão disponíveis em sua implantação Enterprise Voice, clique em **Selecionar**. Em **Selecionar Regras de Conversão**, clique nas regras que deseja associar ao tronco e clique em **OK**.

    - Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**. Para obter detalhes sobre regras de conversão, consulte [Regras de conversão em Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).

    - Para editar uma regra de conversão que já está associada ao tronco, clique no nome da regra e, depois, em **Mostrar detalhes**.

    - Para copiar uma regra de conversão existente a fim de usá-la como ponto de partida para definir uma nova regra, clique no nome da regra, em seguida, em **Copiar** e, então, clique em **Colar**.

    - Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em **Remover**.

      > [!CAUTION]
      > Não associe regras de conversão a um tronco se você tiver configurado as regras de conversão no ponto de tronco associado, pois as duas regras podem entrar em conflito.

16. Certifique-se de que as regras de conversão do tronco sejam organizadas na ordem correta. Para alterar a posição de uma regra na lista, realça o nome da regra e clique na seta para cima ou para baixo.

    > [!IMPORTANT]
    > Skype for Business Server percorre a lista de regras de conversão da parte superior para baixo e usa a primeira regra que corresponde ao número discado. Se você configurar um tronco de modo que um número discado possa corresponder a mais de uma regra de conversão, certifique-se de que as regras mais restritivas estejam classificadas acima das regras menos restritivas. Por exemplo, se você tiver incluído uma regra de conversão que corresponde a qualquer número de 11 dígitos e uma regra de conversão que corresponde a apenas  números de 11 dígitos que começam com +1425, certifique-se de que a regra que corresponde a qualquer número de 11 dígitos seja classificação abaixo da regra mais restritiva.

17. Depois de concluir a configuração do tronco, clique em **OK**.

18. Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**.

    > [!NOTE]
    > Sempre que você criar ou modificar uma configuração de tronco, execute o comando **Confirmar tudo** para publicar a alteração da configuração. Para obter detalhes, [consulte Publicar alterações pendentes na](voice-route-config-changes.md) configuração de roteamento de voz Skype for Business na documentação Operações.

## <a name="see-also"></a>Confira também

[Configurar um tronco com bypass de mídia Skype for Business Server](configure-trunk-with-media-bypass.md)

[Definindo regras de conversão](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules)