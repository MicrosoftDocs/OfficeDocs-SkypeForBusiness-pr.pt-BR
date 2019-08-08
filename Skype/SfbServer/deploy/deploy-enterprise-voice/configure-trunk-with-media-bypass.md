---
title: Configurar um tronco com bypass de mídia no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
description: 'Resumo: configurar um tronco com bypass de mídia habilitado para o Skype for Business Server. Isso permitirá que você minimize o número de servidores de mediação, supondo que o seu provedor de tronco SIP dê suporte a ele.'
ms.openlocfilehash: 3b51cedfbead08cd70b543e9019c351adcc2a4eb
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233668"
---
# <a name="configure-a-trunk-with-media-bypass-in-skype-for-business-server"></a>Configurar um tronco com bypass de mídia no Skype for Business Server

**Resumo:** Configurar um tronco com bypass de mídia habilitado para o Skype for Business Server. Isso permitirá que você minimize o número de servidores de mediação, supondo que o seu provedor de tronco SIP dê suporte a ele.

Siga estas etapas se desejar configurar um tronco com o bypass de mídia habilitado. Para configurar um tronco com bypass de mídia desabilitado, consulte [configurar um tronco sem bypass de mídia no Skype for Business Server](configure-trunk-without-media-bypass.md).

O bypass de mídia é útil quando você deseja minimizar o número de servidores de mediação implantados. Para obter mais informações, consulte [planejar o bypass de mídia no Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)

É altamente recomendável habilitar o bypass de mídia. No entanto, antes de habilitá-lo em um tronco SIP, confirme se seu provedor do tronco SIP oferece suporte ao bypass de mídia e pode acomodar os requisitos para habilitar o cenário com êxito. Especificamente, o provedor deve ter os endereços IP dos servidores na rede interna da sua organização.

> [!NOTE]
> O bypass de mídia não interoperará com todos gateways de Rede de Telefonia Comutada Pública (PSTN), IP-BX e SBC (Controlador de Borda de Sessão). A Microsoft testou um conjunto de gateways PSTN e SBCs com parceiros certificados. O bypass de mídia só tem suporte com produtos e versões listados na [infraestrutura de telefonia para a página do Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) .

Uma configuração de tronco, como descrita abaixo, agrupa um conjunto de parâmetros que são aplicados a troncos atribuídos a essa configuração de tronco. O escopo de uma configuração de tronco específica pode ser global (para todos os troncos que não têm configuração de site ou pool mais específica), ou para um site ou pool. A configuração de tronco no nível do pool é usada para fazer o escopo de uma configuração de tronco específico para um único tronco.

### <a name="to-configure-a-trunk-with-media-bypass"></a>Para configurar um tronco com bypass de mídia

1. Abrir o painel de controle do Skype for Business Server

2. Na barra de navegação à esquerda, clique em **Roteamento de Voz** e depois, em **Configuração do Tronco**.

3. Na página **Configuração do Tronco**, use um dos métodos a seguir para configurar um tronco:

   - Dê um duplo clique em um tronco existente (por exemplo, o tronco **Global**) para exibir a caixa de diálogo **Editar Configuração do Tronco**.

   - Clique em **Novo** e depois, selecione um escopo para a nova configuração de tronco:

   - **Tronco do site**: Escolha o site para esta configuração de tronco em **Selecionar um Site** e depois, clique em **OK**. Observe que se uma configuração de tronco já tiver sido criada para um site, o site não aparecerá em **Selecionar um Site**. Essa configuração de tronco será aplicada a todos os troncos no site.

   - **Tronco do pool**: Escolha o nome do tronco ao qual essa configuração de tronco se aplica. Esse tronco pode ser o tronco raiz ou qualquer tronco adicional definido no construtor de topologias. Em **Selecionar um Serviço**, clique em **OK**. Observe que se uma configuração de tronco já tiver sido criada para um tronco específico, o tronco não aparecerá em **Selecionar um Serviço**.

      > [!NOTE]
      > Depois de selecionar o escopo da configuração de tronco, ele não poderá ser alterado. > o campo **nome** está previamente preenchido com o nome do site ou serviço associado de configuração de tronco e não pode ser alterado.

4. Especifique um valor em **Máximo de caixas de diálogo iniciais com suporte**. Este é o número máximo de respostas bifurcadas que um gateway de rede de telefonia comutada pública (PSTN), IP-PBX, ou Controlador de Borda de Sessão (SBC) ITSP pode receber para um INVITE enviado para o Servidor de Mediação. O valor padrão é 20.

    > [!NOTE]
    > Antes de alterar este valor, consulte seu provedor de serviços ou fabricante do equipamento para detalhes sobre as capacidades do seu sistema.

5. Selecione uma das seguintes opções de **Nível de suporte de criptografia**:

   - **Requerido**: A criptografia do protocolo de transporte seguro em tempo real (SRTP) deve ser usada para ajudar a proteger o tráfego entre o Servidor de Mediação e o gateway ou PBX (private branch exchange).

   - **Opcional**: a criptografia SRTP será usada se o provedor de serviços ou fabricante do equipamento oferecer suporte a ela.

   - **Sem Suporte**: a criptografia SRTP não é suportada pelo provedor de serviços ou fabricante do equipamento e, portanto, não será usada.

6. Selecione a opção **Habilitar bypass de mídia** se você deseja que que a mídia desvie do Servidor de Mediação para processamento pelo ponto do tronco.

    > [!IMPORTANT]
    > Para que o bypass de mídia funcione com êxito, o gateway PSTN gateway, IP-PBX ou Controlador de Borda de Sessão ITSP deve oferecer suporte a determinados recursos. Para obter detalhes, consulte [plano de bypass de mídia no Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

7. Selecione a opção **Processamento de mídia centralizado** se houver um ponto de terminação de mídia conhecido (por exemplo, um gateway PSTN em que a terminação de mídia tem o mesmo IP da terminação de sinalização). Desmarque esta opção se o tronco não possuir um ponto de terminação de mídia conhecido.

8. Se o par de troncos der suporte para receber solicitações de referência SIP do servidor de mediação, marque a caixa de seleção **habilitar o envio para o gateway** .

    > [!NOTE]
    > Se esta opção for desabilitada enquanto a opção **Habilitar bypass de mídia** estiver selecionada, configurações adicionais são necessárias. Se o ponto do tronco não oferecer suporte ao recebimento de solicitações SIP REFER do Servidor de Mediação e o bypass de mídia estiver habilitado, você também deve executar o cmdlet **Set-CsTrunkConfiguration** para desabilitar o RTCP para chamadas ativas e em espera para suportar as condições adequadas para bypass de mídia. Como alternativa, é possível selecionar **Ativar referenciamento usando controle de chamada de terceiros** se quiser que as chamadas transferidas contornem a mídia e o gateway não suporte solicitações SIP REFER.

9. (Opcional) Para permitir roteamento entre troncos, associe e configure os registros de uso de PSTN a essa configuração de tronco. Os usos de PSTN associados a essa configuração de tronco serão aplicados a todas as chamadas recebidas por meio do tronco que não se originam de um ponto de extremidade do Skype for Business Server. Para gerenciar os registros de uso de PSTN associados à configuração de tronco, use um dos métodos a seguir:

   - Para selecionar um ou mais registros de uma lista de todos os registros de uso PSTN disponíveis na sua implantação do Enterprise Voice, clique em **selecionar**. Realce os registros que você deseja associar a essa configuração de tronco e depois, clique em **OK**.

   - Para remover um registro de uso de PSTN desta configuração de tronco, selecione o registro e clique em **Remover**.

   - Para definir um novo registro de uso PSTN e associá-lo a essa configuração de tronco, faça o seguinte:

     a. Clique em **Novo**.

     b. No campo **Nome**, especifique um nome descritivo que seja exclusivo para o registro.

     > [!NOTE]
     > O nome do registro de uso de PSTN deve ser exclusivo dentro de implantação do Enterprise Voice. Após a gravação do registro, o campo **Nome** não pode ser editado.

     c. Use um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:

     - Para selecionar uma ou mais rotas da lista de todas as rotas disponíveis na sua implantação do Enterprise Voice, clique em **selecionar**. Destaque as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.

     - Para remover uma rota do registro de uso do PSTN, selecione a rota e clique em **Remover**.

   - Para definir uma nova rota e associá-la ao registro de uso do PSTN, clique em **Novo**. Para obter detalhes, consulte [criar ou modificar uma rota de voz no Skype for Business](create-or-modify-a-voice-route.md).

     - Para editar uma rota que está associada a esse registro de uso do PSTN, selecione a rota e clique em **Exibir detalhes**.

     d. Clique em **OK**.

     - Para editar um registro de uso de PSTN que já está associado a essa configuração de tronco, faça o seguinte:

       a. Selecione o registro de uso do PSTN que você deseja editar e clique em **Mostrar detalhes**.

       b. Use um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:

   - Para selecionar uma ou mais rotas da lista de todas as rotas disponíveis na sua implantação do Enterprise Voice, clique em **selecionar**. Destaque as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.

   - Para remover uma rota do registro de uso do PSTN, selecione a rota e clique em **Remover**.

   - Para definir uma nova rota e associá-la ao registro de uso do PSTN, clique em **Novo**. Para obter detalhes, consulte [criar ou modificar uma rota de voz no Skype for Business](create-or-modify-a-voice-route.md).

   - Para editar uma rota que está associada a esse registro de uso do PSTN, selecione a rota e clique em **Exibir detalhes**.

     c. Clique em **OK**.

     > [!IMPORTANT]
     > É importante associar registros de uso PSTN de acordo com o peer do servidor de mediação associado ao tronco que está sendo configurado. Se o peer do servidor de mediação for um gateway PSTN ou um controle de borda de sessão (SBC), é altamente recomendável que a configuração de troncos não esteja associada a um registro de uso PSTN que roteia para um destino PSTN ou qualquer outro sistema downstream conectado via Skype para Business Server.

10. Organize os registros de uso do PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, selecione o registro de uso PSTN e clique nas setas para cima ou para baixo.

    > [!IMPORTANT]
    > A ordem na qual PSTN registros de uso são listados na configuração de tronco é significativa. O Skype for Business Server percorre a lista de cima para baixo.

11. **Enable RTP Latching** deve ser selecionado para permitir desvio de mídia para clientes atrás de uma NAT (conversão de endereço de rede) ou firewall, e um SBC que suporte travamento.

12. **Habilitar o histórico de chamadas** de encaminhamento deve ser selecionado para permitir o envio de informações de histórico de chamadas para o par de gateways do servidor de mediação.

13. **Habilitar encaminhar os dados de identidades p-** declarados devem ser selecionados para permitir que as informações do originador da chamada p-Asserted-Identity (pai) sejam encaminhadas entre o lado do servidor de mediação e o lado do gateway (e vice-versa), quando estiverem presentes.

14. **Enable outbound routing failover timer** deve ser selecionado para permitir failover rápido. O gateway associado a esse tronco pode fornecer notificações em 10 segundos de que está processando uma chamada de saída. O redirecionamento para outro tronco ocorrerá se essa notificação não for recebida pelo servidor de mediação. Em redes onde a latência pode atrasar o tempo de resposta ou o gateway levar mais de 10 segundos para responder, o failover rápido deverá ser desativado.

15. (Opcional) Associe e configure as **regras de conversão do número de chamada** do tronco. Essas regras de conversão se aplicam ao número chamado para chamadas de saída.

    - Para escolher uma ou mais regras de uma lista de todas as regras de tradução que estão disponíveis na sua implantação do Enterprise Voice, clique em **selecionar**. Em **Selecionar Regras de Conversão**, clique nas regras que você deseja associar com o tronco, e depois em **OK**.

    - Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**. Para obter detalhes sobre as regras de tradução, consulte [regras de tradução no Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).

    - Para editar uma regra de conversão que já esteja associada ao tronco, clique no nome da regra e clique em **Exibir detalhes**.

    - Para copiar uma regra de conversão existente para usar como ponto de partida para definir uma nova regra, clique no nome da regra e clique em **Copiar** e clique em **Copiar**.

    - Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em **Remover**.

    > [!CAUTION]
    > Não associe regras de conversão a um tronco se não houver regras de conversão configuradas no ponto do tronco associado porque as duas regras podem entrar em conflito.

16. (Opcional) Associe e configure as **regras de conversão de números chamados** do tronco. As regras de conversão se aplicam ao número chamado em uma chamada de saída.

    - Para escolher uma ou mais regras de uma lista de todas as regras de tradução que estão disponíveis na sua implantação do Enterprise Voice, clique em **selecionar**. Em **Selecionar Regras de Conversão**, clique nas regras que você deseja associar com o tronco, e depois em **OK**.

    - Para definir uma nova regra de conversão e associá-la ao tronco, clique em **Novo**. Para obter detalhes sobre as regras de tradução, consulte [regras de tradução no Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).

    - Para editar uma regra de conversão que já esteja associada ao tronco, clique no nome da regra e clique em **Exibir detalhes**.

    - Para copiar uma regra de conversão existente para usar como ponto de partida para definir uma nova regra, clique no nome da regra e clique em **Copiar** e clique em **Copiar**.

    - Para remover uma regra de conversão do tronco, destaque o nome da regra e clique em **Remover**.

    > [!CAUTION]
    > Não associe regras de conversão a um tronco se não houver regras de conversão configuradas no ponto do tronco associado porque as duas regras podem entrar em conflito.

17. Verifique se as regras de tradução do tronco estão organizadas na ordem correta. Para alterar a posição de uma regra na lista, realce o nome da regra e clique na seta para cima ou para baixo.

    > [!IMPORTANT]
    > O Skype for Business Server percorre a lista de regras de tradução da parte superior para baixo e usa a primeira regra que corresponde ao número discado. Se você configurar um tronco de forma que um número discado possa corresponder a mais de uma regra de conversão, certifique-se de que as regras mais restritivas estejam classificadas acima das regras menos restritivas. Por exemplo, se você tiver incluído uma regra de tradução que corresponda a qualquer número de 11 dígitos e uma regra de tradução que corresponda apenas a números de 11 dígitos que comecem com + 1425, certifique-se de que a regra que corresponde a qualquer número de 11 dígitos esteja classificada *abaixo* do mais restritivo das.

18. Ao terminar de configurar o tronco, clique em **OK**.

19. Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**.

    > [!NOTE]
    > Sempre que criar ou modificar uma configuração de tronco, você deve executar o comando **Confirmar tudo** para publicar a alteração na configuração. Para obter detalhes, consulte [publicar alterações pendentes na configuração de roteamento de voz no Skype for Business](voice-route-config-changes.md) na documentação de operações.

Depois de configurar o tronco, continue a configuração do bypass de mídia escolhendo entre as opções de bypass de mídia global, conforme descrito em [implantar bypass de mídia no Skype for Business Server](deploy-media-bypass.md) na documentação de implantação.
## <a name="see-also"></a>Confira também

[Configurar um tronco sem bypass de mídia no Skype for Business Server](configure-trunk-without-media-bypass.md)

[Implantar bypass de mídia no Skype for Business Server](deploy-media-bypass.md)

[Definindo regras de tradução](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)

[Configurar o bypass de mídia](https://technet.microsoft.com/library/f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8.aspx)

