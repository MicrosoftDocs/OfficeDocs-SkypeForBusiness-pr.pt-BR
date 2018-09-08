---
title: Configurar um tronco sem bypass de mídia no Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
description: 'Resumo: Configure um tronco sem bypass de mídia habilitado para Skype para Business Server.'
ms.openlocfilehash: fa912286dd89acaa75781d8175f6820444adc6ea
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884172"
---
# <a name="configure-a-trunk-without-media-bypass-in-skype-for-business-server"></a>Configurar um tronco sem bypass de mídia no Skype para Business Server

**Resumo:** Configure um tronco sem bypass de mídia habilitado para Skype para Business Server.

Se quiser configurar um tronco com desvio de mídia desabilitado, siga estas etapas. Se você deseja configurar um tronco com bypass de mídia habilitado, consulte [Configurar um tronco com media bypass no Skype para Business Server](configure-trunk-with-media-bypass.md).

Uma configuração de tronco, como descrito abaixo, agrupa um conjunto de parâmetros que são aplicados a troncos designados com essa configuração. Uma determinada configuração de tronco pode ter o escopo de forma global (a todos os troncos que não têm uma configuração de site ou pool mais específica), para um site ou para um pool. A configuração de tronco no nível do pool é usada para definir o escopo de uma configuração específica de um tronco individual.

### <a name="to-configure-a-trunk-without-media-bypass"></a>Para configurar um tronco sem bypass de mídia

1. Abra o Skype para painel de controle do servidor de negócios.

2. Na barra de navegação à esquerda, clique em **Roteamento de Voz** e depois, em **Configuração do Tronco**.

3. Na página **Configuração do Tronco**, use um dos métodos a seguir para configurar um tronco:

   - Dê um duplo clique em um tronco existente (por exemplo, o tronco **Global**) para exibir a caixa de diálogo **Editar Configuração do Tronco**.

   - Clique em **Novo** e depois, selecione um escopo para a nova configuração de tronco:

   - **Tronco de site**: escolha o site para essa configuração de tronco em **Selecionar um Site**e clique em **Okey**. Observe que se uma configuração de tronco já tiver sido criada para um site, o site não aparecerá em **Selecionar um Site**. Essa configuração de tronco será aplicada a todos os troncos do site.

   - **Tronco do pool**: escolha um nome para o tronco ao qual essa configuração de tronco se aplica em **Selecionar um Serviço** e clique em **OK**. Esse tronco pode ser o tronco raiz, ou qualquer definidos no construtor de topologia de troncos adicionais. Observe que se uma configuração de tronco já tiver sido criada para um tronco específico, o tronco não aparecerá em **Selecionar um Serviço**.

    > [!NOTE]
    > Depois de selecionar o escopo da configuração de tronco, ele não poderá ser alterado. > O campo **nome** é preenchido previamente com o nome da site do configuração do tronco ou serviço associado e não pode ser alterado.

4. Selecione uma das seguintes opções de **Nível de suporte de criptografia**:

   - **Requerido**: a criptogaafia do Protocolo de Transporte Seguro em Tempo Real (SRTP) deve ser usada para ajudar a proteger o tráfego entre o Servidor de Mediação e o gateway ou PBX (private branch exchange).

   - **Opcional**: a criptografia SRTP será usada se o provedor de serviços ou fabricante do equipamento oferecer suporte a ela.

   - **Sem Suporte**: a criptografia SRTP não é suportada pelo provedor de serviços ou fabricante do equipamento e, portanto, não será usada.

5.  Certifique-se de que a caixa de seleção **Habilitar bypass de mídia** esteja desmarcada.

6. Marque a caixa de seleção **Processamento de mídia centralizado** se houver um ponto de encerramento de mídia conhecido [por exemplo, um gateway PSTN (Rede Telefônica Pública Comutada) no qual o encerramento de mídia tenha o mesmo IP que o encerramento de sinalização]. Desmarque essa caixa de seleção se o tronco não tiver um ponto de encerramento de mídia conhecido.

7. Se o ponto do tronco suporta o recebimento de solicitações SIP REFER do servidor de mediação, marque a caixa de seleção **Habilitar o envio de referência ao gateway** .

8. (Opcional) Para permitir roteamento entre troncos, associe e configure os registros de uso de PSTN a essa configuração de tronco. Os usos da PSTN associados a essa configuração de tronco serão aplicados para todas as chamadas recebidas por meio do tronco que não é provenientes de um Skype para ponto de extremidade do servidor de negócios. Para gerenciar os registros de uso de PSTN associados à configuração de tronco, use um dos métodos a seguir:

   - Para selecionar um ou mais registros de uma lista de todos os registros de uso PSTN disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**. Realce os registros que você deseja associar a essa configuração de tronco e depois, clique em **OK**.

   - Para remover um registro de uso de PSTN desta configuração de tronco, selecione o registro e clique em **Remover**.

   - Para definir um novo registro de uso PSTN e associá-lo a essa configuração de tronco, faça o seguinte:

     a. Clique em **Novo**.

     b. No campo **Nome**, especifique um nome descritivo que seja exclusivo para o registro.

     > [!NOTE]
     > O nome do registro de uso de PSTN deve ser exclusivo dentro de implantação do Enterprise Voice. Após a gravação do registro, o campo **Nome** não pode ser editado.

     c. Use um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:

     - Para selecionar uma ou mais rotas da lista de todas as rotas disponíveis na implantação do Enterprise Voice, clique em **Selecionar**. Destaque as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.

     - Para remover uma rota do registro de uso do PSTN, selecione a rota e clique em **Remover**.

     - Para definir uma nova rota e associá-la ao registro de uso do PSTN, clique em **Novo**. Para obter detalhes, consulte [criar ou modificar uma rota de voz no Skype para negócios](create-or-modify-a-voice-route.md).

     - Para editar uma rota que está associada a esse registro de uso do PSTN, selecione a rota e clique em **Exibir detalhes**.

     d. Clique em **OK**.

   - Para editar um registro de uso de PSTN que já está associado a essa configuração de tronco, faça o seguinte:

    a. Selecione o registro de uso do PSTN que você deseja editar e clique em **Mostrar detalhes**.

    b. Use um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:

     - Para selecionar uma ou mais rotas da lista de todas as rotas disponíveis na implantação do Enterprise Voice, clique em **Selecionar**. Destaque as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.

     - Para remover uma rota do registro de uso do PSTN, selecione a rota e clique em **Remover**.

     - Para definir uma nova rota e associá-la ao registro de uso do PSTN, clique em **Novo**. Para obter detalhes, consulte [criar ou modificar uma rota de voz no Skype para negócios](create-or-modify-a-voice-route.md).

     - Para editar uma rota que está associada a esse registro de uso do PSTN, selecione a rota e clique em **Exibir detalhes**.

    c. Clique em **OK**.

     > [!IMPORTANT]
     > É importante associar os registros de uso PSTN de acordo com o ponto do servidor de mediação associado ao tronco está sendo configurado. Se o ponto de servidor de mediação é um gateway PSTN ou um controlador de borda de sessão (SBC), é altamente recomendável que a configuração do tronco não esteja associada a um registro de uso PSTN rotas para um destino de PSTN ou outros sistemas de downstream conectadas por meio do Skype para o servidor de negócios.

9. Organize os registros de uso do PSTN para obter o melhor desempenho. Para alterar a posição do registro na lista, selecione o registro de uso PSTN e clique em cima ou para baixo setas.

    > [!IMPORTANT]
    > A ordem na qual PSTN registros de uso são listados na configuração de tronco é significativa. Skype para Business Server percorre a lista de cima para baixo.

10. **Habilitar engatador RTP** deve ser selecionado para habilitar bypass de mídia para clientes sob um NAT ou firewall e um SBC que dê suporte ao engatador.

11. **Habilitar o histórico de encaminhamento de chamada** deve ser selecionado para habilitar o envio de informações de histórico de chamadas ao par do gateway do servidor de mediação.

12. **Habilitar encaminhamento de dados P-Asserted-Identity** deve ser selecionado para habilitar informações do originador de chamadas PAI sejam encaminhadas entre o lado do servidor de mediação e o lado do gateway (e vice-versa) quando a apresentar.

13. **Enable outbound routing failover timer** deve ser selecionado para permitir failover rápido. O gateway associado a esse tronco pode fornecer notificações em 10 segundos de que está processando uma chamada de saída. Redirecionamento para outro tronco ocorrerá se essa notificação não for recebida pelo servidor de mediação. Em redes onde a latência pode atrasar o tempo de resposta ou o gateway levar mais de 10 segundos para responder, o failover rápido deverá ser desativado.

14. (Opcional) Associe e configure as **regras de conversão do número de chamada** do tronco. Essas regras de conversão se aplicam ao número chamado para chamadas de saída.

   - Para escolher uma ou mais regras de uma lista de todas as regras de conversão que estão disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**. Em **Selecionar Regras de Conversão**, clique nas regras que você deseja associar com o tronco, e depois em **OK**.

   - Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**. Para obter detalhes sobre as regras de conversão, consulte [regras de conversão no Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).

   - Para editar uma regra de conversão que já esteja associada ao tronco, clique no nome da regra e clique em **Exibir detalhes**.

   - Para copiar uma regra de conversão existente para usar como ponto de partida para definir uma nova regra, clique no nome da regra e clique em **Copiar** e clique em **Copiar**.

   - Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em **Remover**.

     > [!CAUTION]
     > Não associe regras de conversão a um tronco se não houver regras de conversão configuradas no ponto do tronco associado porque as duas regras podem entrar em conflito.

15. (Opcional) Associe e configure as **regras de conversão de números chamados** do tronco. As regras de conversão se aplicam ao número chamado em uma chamada de saída.

   - Para escolher uma ou mais regras de uma lista de todas as regras de conversão que estão disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**. Em **Selecionar Regras de Conversão**, clique nas regras que você deseja associar com o tronco, e depois em **OK**.

  - Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**. Para obter detalhes sobre as regras de conversão, consulte [regras de conversão no Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).

   - Para editar uma regra de conversão que já esteja associada ao tronco, clique no nome da regra e clique em **Exibir detalhes**.

   - Para copiar uma regra de conversão existente para usar como ponto de partida para definir uma nova regra, clique no nome da regra e clique em **Copiar** e clique em **Copiar**.

   - Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em **Remover**.

     > [!CAUTION]
     > Não associe regras de conversão a um tronco se não houver regras de conversão configuradas no ponto do tronco associado porque as duas regras podem entrar em conflito.

16. Certifique-se de que as regras de conversão do tronco são organizadas na ordem correta. Para alterar a posição de uma regra na lista, destaque o nome da regra e clique em cima ou seta para baixo.

    > [!IMPORTANT]
    > Skype para Business Server percorre a lista de regras de conversão de cima para baixo e usa a primeira regra que corresponde ao número discado. Se você configurar um tronco de forma que um número discado possa corresponder a mais de uma regra de conversão, certifique-se de que as regras mais restritivas estejam classificadas acima das regras menos restritivas. Por exemplo, se você tiver incluído uma regra de conversão que corresponde a qualquer número de 11 dígitos e uma regra de conversão que corresponda apenas os números de 11 dígitos que começam com + 1425, certifique-se que a regra que corresponde a qualquer número de 11 dígitos é classificada *abaixo* mais restritivo regra.

17. Ao terminar de configurar o tronco, clique em **OK**.

18. Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**.

    > [!NOTE]
    > Sempre que criar ou modificar uma configuração de tronco, você deve executar o comando **Confirmar tudo** para publicar a alteração na configuração. Para obter detalhes, consulte [Publish alterações pendentes para a configuração de roteamento de voz no Skype para negócios](voice-route-config-changes.md) na documentação operações.

## <a name="see-also"></a>Consulte também

[Configurar um tronco com bypass de mídia no Skype para Business Server](configure-trunk-with-media-bypass.md)

[Definindo regras de conversão](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)

