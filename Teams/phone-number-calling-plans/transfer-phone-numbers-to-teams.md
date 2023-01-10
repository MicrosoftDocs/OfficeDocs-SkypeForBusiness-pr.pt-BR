---
title: Transferir números de telefone para o Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: tonysmit
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como usar o assistente de portabilidade para transferir seu número de telefone do provedor de serviços atual para o Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 20c4caf97c5344d48f93feed47dc181495dd318d
ms.sourcegitcommit: 1398c778e46b0d81c9710cd70d3818a2b7af995a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2023
ms.locfileid: "69749037"
---
# <a name="transfer-phone-numbers-to-microsoft-teams"></a>Transferir números de telefone para o Microsoft Teams

Use o assistente de portabilidade no centro de administração do Microsoft Teams para transferir seus números de telefone do provedor de serviços atual para o Teams. Depois que você portar seus números de telefone para o Teams, a Microsoft se tornará seu provedor de serviços e cobrará por esses números de telefone.

Antes de começar, recomendamos que você examine as informações em [O que é uma ordem de porta?](port-order-overview.md) Se você tiver números de serviço para pontes de conferência discada, atendentes automáticos ou outros números de serviço, números de telefone gratuitos ou tiver mais de 999 números de telefone de usuário (assinante) que você precisa transferir para o Teams, consulte [Gerenciar números de telefone para sua organização baixar os formulários corretos](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) e enviá-los para nós.

  > [!NOTE]
  > Processamos pedidos de porta para transferir números de telefone apenas em Estados Unidos dias úteis e não em feriados ou fins de semana.
  >
  > A disponibilidade de portabilidade para números de telefone gratuitos pode variar de acordo com o país e a região. Para localizar mais, consulte documentos específicos do país ou da região para ver o suporte disponível para o serviço de portabilidade.

## <a name="create-a-port-order-and-transfer-your-phone-numbers-to-teams"></a>Criar um pedido de porta e transferir seus números de telefone para o Teams

> [!NOTE]
> Se você tiver problemas com o processo de portabilidade no centro de administração do Teams, poderá [enviar manualmente uma ordem de porta](manually-submit-port-order.md) para o Service Desk do TNS. Para obter o formulário necessário para enviar manualmente um pedido de porta, selecione seu país ou região na lista suspensa em [Gerenciar números de telefone para sua organização](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

1. Na navegação à esquerda do centro de administração do Microsoft Teams, acesse **números de telefone de** **voz** > . Selecione **Números** e selecione **Porta** para iniciar o assistente de portabilidade.
2. Examine as informações na página **Introdução** e, quando estiver pronto, selecione **Avançar**.
3. Na página **Selecionar local e tipo de número** , especifique o seguinte e selecione **Avançar**:

    - **País ou região**: país ou região em que você está recebendo números.
    - **Tipo de número de telefone**: tipo de número, como números geográficos ou gratuitos.
    - **Números atribuídos a: a** que os números são atribuídos. Por exemplo, usuários ou recursos de conferência ou voz.

4. Na página **Adicionar informações da conta** , conclua o seguinte e selecione **Avançar**.

    > [!IMPORTANT]
    > As informações exibidas nesta página são determinadas pelo país ou região e tipo de número. Cada país e região tem regulamentos diferentes sobre as informações necessárias para portar números. O que você vê nesta página pode ser diferente do descrito aqui.

    - **Detalhes do pedido**: 
        - **Nome do** pedido: nome do seu pedido
        - **Emails de notificação**: Email endereços para receber notificações de pedido. Se você inserir vários endereços de email, separe cada um com um ponto e vírgula.
        - **Data transferida**: data de transferência emitida pelo provedor de serviços atual.
    - **Detalhes do número de telefone**
        - **Tipo** de porta: se você estiver fazendo uma porta completa para transferir todos os seus números ou uma porta parcial para transferir alguns de seus números.
    - **Pessoa solicitando detalhes**  
        - O nome da organização e os detalhes de contato da pessoa que solicita a transferência.
    - **Detalhes do provedor atual**
        - **Número de telefone de cobrança (BTN)**: seu BTN no formato E.164, que requer um sinal + para preparar o número. Por exemplo, para um número de América do Norte, use o formato +1XXXYYZZZZ.
        - Outros detalhes, incluindo o nome do provedor de serviços atual, o número da conta e o endereço do serviço.
            
5. Na página **Adicionar números** , **selecione Selecionar um arquivo**, navegue até e selecione o arquivo CSV que contém os números de telefone que você deseja transferir e selecione **Avançar**.  

    > [!NOTE]
    > O arquivo CSV deve ter apenas uma coluna com um cabeçalho chamado **PhoneNumber**. Cada número de telefone deve estar em uma linha separada e pode ser apenas dígitos ou no formato E.164.

6. Na página **Concluir seu pedido** , selecione **Carregar uma Carta de Autorização assinada** para carregar uma cópia digitalizada da LOA (Carta de Autorização) assinada.

    Se você ainda não tiver baixado e assinado a LOA, faça o seguinte:
    
    1. Selecione **Baixar o modelo** para baixar o LOA para seu país ou região. 
    2. Imprima o LOA.
    3. Tenha o LOA assinado pela pessoa que está autorizada a fazer alterações na conta.
    4. Examine o LOA assinado e selecione **Carregar uma Carta de Autorização assinada** para carregá-la.

    > [!NOTE]
    > Depois de carregar sua LOA, envie seu pedido. Apenas carregar o LOA não é suficiente. Você também precisa enviar o pedido para que ele seja processado.

7. Examine os detalhes do pedido e selecione **Enviar**.

## <a name="what-happens-next"></a>O que acontece agora?

Quando recebermos seu pedido de porta, você receberá um email que verifica sua solicitação. Sua solicitação é marcada e atualizada diariamente e você será notificado sobre seu progresso e status no email. Se sua solicitação de porta for rejeitada pela operadora, entre em contato com o [Service Desk do TNS](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md) para obter assistência.

Para exibir o status da sua ordem de porta, na navegação à esquerda do centro de administração do Microsoft Teams, acesse **pedidos da Porta** de **Voz** >  e selecione **Histórico de pedidos**. Cada status de pedido de porta está listado na coluna **Status** . Para saber mais, confira [Qual é o status dos pedidos de porta?](port-order-status.md)


## <a name="reporting-telephone-number-issues"></a>Relatando problemas de número de telefone?

Se você notar problemas com os números portados nas primeiras 24 a 48 horas após a conclusão da porta, entre em contato com o [Service Desk do TNS](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md). Para quaisquer problemas além de 48 horas, entre em contato com a equipe de Suporte da Microsoft.

## <a name="related-articles"></a>Artigos relacionados

- [O que é um pedido de portabilidade?](port-order-overview.md)
- [Diferentes tipos de números de telefone utilizados para Planos de Chamadas](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Gerenciar os números de telefone de sua organização](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Termos e condições das Chamadas de Emergência](../emergency-calling-terms-and-conditions.md)
- [Rótulo de isenção de isenção de responsabilidade de chamada de emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
