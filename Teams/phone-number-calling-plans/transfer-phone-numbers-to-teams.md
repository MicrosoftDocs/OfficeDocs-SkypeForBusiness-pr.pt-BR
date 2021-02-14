---
title: Transferir números de telefone para o Microsoft Teams
author: cichur
ms.author: v-cichur
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
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar o assistente de portação para transferir seu número de telefone do provedor de serviços atual para o Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 52dd8a2a1dcbc14930695efd52141ce3b1842458
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812961"
---
# <a name="transfer-phone-numbers-to-microsoft-teams"></a>Transferir números de telefone para o Microsoft Teams

[!INCLUDE [preview-feature](../includes/preview-feature.md)]

Use o assistente de portação no Centro de administração do Microsoft Teams para transferir seus números de telefone de seu provedor de serviços atual para o Teams. Depois que você portuar seus números de telefone para o Teams, a Microsoft se tornará seu provedor de serviços e cobrará você por esses números de telefone.

Antes de começar, recomendamos que você revise as informações em [O que é um pedido de portabilidade?](port-order-overview.md) Se você tiver números de serviço para pontes de conferência discda, atender automaticamente ou outros números de serviço, números de chamada gratuita ou [](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) tiver mais de 999 números de telefone de usuário (assinante) que precisa transferir para o Teams, consulte Gerenciar números de telefone de sua organização para baixar os formulários corretos e enviá-los para nós.

  > [!NOTE]
  > Processam pedidos de portabilidade para transferência de números de telefone somente em dias úteis nos Estados Unidos e não em feriados públicos ou finais de semana.

## <a name="create-a-port-order-and-transfer-your-phone-numbers-to-teams"></a>Criar um pedido de portabilidade e transferir seus números de telefone para o Teams

> [!NOTE]
> Atualmente, você pode usar este assistente para obter números de telefone para **o Reino Unido, Estados Unidos e Canadá.** Para obter números de telefone para outros países e regiões, você pode [enviar manualmente um pedido de portabilidade.](manually-submit-port-order.md) Para obter o formulário de que você precisa para enviar manualmente um pedido de portabilidade, selecione seu país ou região na listada em Gerenciar números de telefone [para sua organização.](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para **números de Telefone** De  >  **Voz.** Clique **em** Números e, em seguida, **clique em Porta** para iniciar o assistente de portabilidade.
2. Revise as informações na **página** De início e, quando estiver pronto, clique em **Próximo.**
3. Na página **Selecionar local e tipo de número,** especifique o seguinte e clique em **Próximo:**

    - **País ou região:** país ou região onde você está recebendo números.
    - **Tipo de número de** telefone: Tipo de número, como números geográficos ou de chamada gratuita.
    - **Números atribuídos a:** a que os números são atribuídos. Por exemplo, usuários, conferência ou recursos de voz.

4. Na página **Adicionar informações da conta,** conclua o seguinte e clique em **Próximo.**

    > [!IMPORTANT]
    > As informações exibidas nesta página são determinadas pelo país ou região e tipo de número. Cada país e região têm regulamentos diferentes sobre as informações necessárias para números de portabilidade. O que você vê nesta página pode ser diferente do que descrevemos aqui.

    - **Detalhes do pedido:** 
        - **Nome do pedido:** Nome do seu pedido
        - **Emails de notificação:** endereços de email para receber notificações de pedido. Se você inserir vários endereços de email, separe-os com ponto e vírgula.
        - **Data de transferência:** data de transferência emitida pelo provedor de serviços atual.
    - **Detalhes do número de telefone**
        - **Tipo de** portabilidade: se você estiver fazendo uma portabilidade completa para transferir todos os seus números ou uma portabilidade parcial para transferir alguns de seus números.
    - **Pessoa solicitando detalhes**  
        - Nome da sua organização e detalhes de contato da pessoa que está solicitando a transferência.
    - **Detalhes do provedor atual**
        - Número de telefone de cobrança **(BTN)**: seu BTN no formato E.164, que requer um sinal + para pré-anexar o número. Por exemplo, para um número da América do Norte, use o formato +1XXXYYYYZZZZ.
        - Outros detalhes, incluindo o nome do provedor de serviços atual, o número da conta e o endereço do serviço.
            
5. Na página **Adicionar números,** clique em Selecionar um **arquivo,** procure e selecione o arquivo CSV que contém os números de telefone que você deseja transferir e clique em **Próximo.**  

    > [!NOTE]
    > O arquivo CSV deve ter apenas uma coluna com um header chamado PhoneNumber. Cada número de telefone deve estar em uma linha separada e pode ser dígitos somente ou no formato E.164.

6. Na página Concluir seu  **pedido,** clique em Carregar uma Carta de Autorização assinada para carregar uma cópia digitalizada da LOA (Carta de Autorização) assinada.

    Se você ainda não baixou e assinou a LOA, faça o seguinte:
    
    1. Clique **em Baixar o modelo** para baixar a LOA para seu país ou região. 
    2. Imprima a LOA.
    3. Faça com que a LOA seja assinada pela pessoa que está autorizada a fazer alterações na conta.
    4. Digitalizar a LOA assinada e, em seguida, clique **em Carregar uma** Carta de Autorização assinada para carregue-a.

    > [!NOTE]
    > Depois de carregar sua LOA, envie seu pedido. Carregar a LOA não é suficiente. Você também precisa enviar o pedido para que ele seja processado.

7. Revise os detalhes do pedido e clique em **Enviar.**


## <a name="what-happens-next"></a>O que acontece agora?

Quando recebermos seu pedido de portabilidade, você receberá um email que verificará sua solicitação. Sua solicitação é marcada e atualizada diariamente, e você será notificado do progresso e do status dele por email. Se a solicitação de portabilidade for rejeitada pela operadora que perdeu, entre em contato com o service [desk PSTN.](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)

Para exibir o status do seu pedido de portabilidade, na navegação à esquerda do Centro de administração do Microsoft Teams, vá para > pedidos de Portabilidade de Voz e clique em  >  Histórico **de pedidos.** Cada status do pedido de portabilidade é listado na **coluna Status.** Para saber mais, veja [Qual é o status dos pedidos de portabilidade?](port-order-status.md)

## <a name="related-topics"></a>Tópicos relacionados

- [O que é um pedido de portabilidade?](port-order-overview.md)
- [Diferentes tipos de números de telefone usados para Planos de Chamadas](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Gerenciar os números de telefone de sua organização](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Termos e condições das Chamadas de Emergência](../emergency-calling-terms-and-conditions.md)
- [Rótulo de aviso de isenção de responsabilidade de Chamada de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
