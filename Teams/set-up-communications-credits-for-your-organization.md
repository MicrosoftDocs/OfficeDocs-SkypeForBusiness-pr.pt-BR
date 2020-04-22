---
title: Configurar Créditos de Comunicação para sua organização
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: bb9f2a8d-f5be-41ed-9d19-25dea5ca9f52
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Licensing
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: 304c08568ee39f69f727d159a5599a3a3ac89ed4
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779738"
---
# <a name="set-up-communications-credits-for-your-organization"></a>Configurar Créditos de Comunicação para sua organização

Você precisará configurar Créditos de Comunicação se quiser usar números gratuitos com o Skype for Business e o Microsoft Teams. Além disso, recomendamos que você configure créditos de comunicações para seus planos de chamadas (domésticos ou internacionais) e usuários de audioconferência que precisem da capacidade de discar para **qualquer destino**. Muitos países/regiões estão incluídos, mas alguns destinos podem não ser incluídos no seu plano de chamadas ou assinaturas de audioconferência. Se você não configurar a cobrança de créditos de comunicações e atribuir uma licença de **créditos de comunicações** aos seus usuários e estiver em minutos para a sua organização (dependendo do seu plano de chamadas ou plano de audioconferência em seu país/região), esses usuários não poderão fazer chamadas nem discar de reuniões de audioconferência. Você pode obter mais informações, incluindo os valores de financiamento recomendados, lendo [o que são créditos de comunicações?](what-are-communications-credits.md)
  
> [!NOTE]
> Para descobrir quanto isso custa, [consulte as taxas aqui](https://go.microsoft.com/fwlink/p/?LinkId=799523 ). 
  
## <a name="step-1-assign-an-audio-conferencing-or-calling-plan-license-to-your-users"></a>Etapa 1: atribuir uma conferência de áudio ou um plano de chamadas a seus usuários

Ao se inscrever, você recebe um determinado número de minutos, dependendo do seu país/região. Você pode ver a quantidade de minutos para a qual vai procurar o país ou região [aqui](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). Depois de usar esses minutos, as chamadas serão desconectadas. Para evitar que isso aconteça, você precisa configurar créditos de comunicações.
  
Para fazer isso, **você precisa atribuir uma conferência de áudio ou uma licença do sistema de telefone** para seus usuários.
  
- Atribua uma licença de **audioconferência** a seus usuários. Consulte [atribuir licenças do Microsoft Teams](assign-teams-licenses.md).
    
    Depois de atribuir essa licença, você precisará configurar a conferência de áudio. Para obter instruções passo a passo, consulte [experimentar ou comprar o áudio videoconferência no Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).
    
- Atribua um **sistema telefônico** e uma licença de plano de chamadas **domésticas ou domésticas e internacionais** para seus usuários. Consulte [atribuir licenças do Microsoft Teams](assign-teams-licenses.md).
    
    > [!NOTE]
    > Embora isso não seja obrigatório para créditos de comunicações, você ainda precisa atribuir um **plano de chamadas domésticas** ou uma licença de **plano de chamadas doméstica e internacional** .
  
    Após atribuir essas licenças, você deverá obter os números de telefone da sua organização e atribuí-los aos usuários. Para obter instruções passo a passo, consulte [configurar planos de chamada](set-up-calling-plans.md).
    
Para obter mais informações, consulte [Licenciamento de Complementos do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a>Etapa 2: configurar créditos de comunicações para sua organização

1. Entre no novo centro de administração do Microsoft 365 com sua conta corporativa ou de estudante.
    
2. Na navegação à esquerda do centro de administração do Microsoft 365, vá para**serviços de compra**de **cobrança** > . Role para baixo e **selecione Complementos**.

3. Selecione **créditos de comunicações**.
    
4. Na página de assinatura **créditos de comunicação** , preencha as informações e clique em **Avançar**:
    
   - **Adicionar fundos** Digite o valor que você deseja adicionar à sua conta. Se você não habilitar a recarga automática, uma vez que esses fundos sejam esgotados, os recursos de chamada habilitados usando créditos de comunicações serão interrompidos (como serviço de chamadas de entrada grátis). Para evitar a necessidade de reabastecer manualmente o saldo dos créditos de comunicações cada vez que seu saldo atingir 0 (zero), recomendamos que você ative o recurso de recarga automática.
    
   - **Recarga automática** A habilitação da recarga automática recarregará sua conta automaticamente quando o saldo ficar abaixo do limite definido.
    
     É recomendável que você use a configuração de **recarga automática** para evitar qualquer interrupção do serviço caso o saldo dos créditos de comunicações atinja 0 (zero). Você receberá um email quando o recarregamento das transações for bem-sucedido, quando o recarregamento de transações falhar (como um cartão de crédito expirado) e quando o saldo dos créditos de comunicações atingir 0 (zero).
    
   - **Valor da recarga** Digite o valor na caixa **recarregar com** que você deseja adicionar à sua conta quando ele atingir o valor de gatilho abaixo.
    
   - **Valor do gatilho** Digite o valor de **quando o saldo ficar abaixo** de a caixa que será usada para ' *disparar* ' a recarga automática. Quando o saldo ficar abaixo desse valor, o valor da recarga será adicionado automaticamente à sua conta.

      > [!NOTE]
     > Os fundos serão aplicados somente aos créditos de comunicação nas tarifas publicadas pela Microsoft quando os serviços forem usados. Os fundos não usados no prazo de 12 meses a contar da data de compra expirarão e serão cancelados. 
     > 
     > A cobrança mensal dos créditos de comunicação só será aplicada se o fundo se tiver sido usado, para saber como verificar o uso mensal, ler o [relatório de uso de PSTN do Skype for Business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)
    
5. Insira suas informações de pagamento e clique em **Fazer pedido**.
    >[!IMPORTANT]
    >Se você for um cliente de licenciamento por volume, você pode escolher seu número enterprise agreement para pagamento. Se você tiver vários números enterprise agreement, você pode escolher qual prefere usar para o pagamento. Você também poderá especificar um número de ordem de compra que será associado ao número do enterprise agreement (se aplicável).
    
Cada organização terá um uso diferente de taxas e volumes do plano de chamadas a serem considerados. You will need to get this type of usage data from your current service provider. As organizações que já usam o Skype for Business online já que o provedor de serviços pode obter dados de uso, revisando-as no >  **centro de administração do Skype for Business****relata** > o relatório de**detalhes de uso de PSTN** .
  
Ao configurar créditos de comunicações, você precisará investigar o uso da chamada para a sua organização para determinar os valores necessários. Você pode obter informações de uso de chamadas examinando o relatório **Detalhes de uso de PSTN**. Este relatório permite exportar os registros de dados de chamadas para o Excel se você precisar armazenar os dados ou criar relatórios personalizados. Para saber como ver o uso, leia o [relatório de uso de PSTN do Skype for Business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report).
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a>Etapa 3: atribuir uma licença de créditos de comunicações aos usuários

1. Entre com sua conta corporativa ou de estudante.
    
2. Na navegação à esquerda do centro de administração do Microsoft 365, vá **para** > usuários**ativos**do usuário e selecione um ou mais usuários na lista.
    
3. Escolha **licenças e aplicativos**.
    
4. Alterne os **créditos de comunicações** para **ativado** para atribuir a licença e, em seguida, selecione **salvar**.
    
    > [!NOTE]
    > Mesmo que você tenha usuários atribuídos a uma licença **Enterprise E5** , ainda é recomendável que você faça isso.
  
## <a name="want-to-know-about-plans-and-pricing"></a>Quer saber mais sobre planos e preços?

Você pode ver os planos e preços visitando um dos seguintes links:
  
- [Planos de Chamadas](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [Planos de audioconferência](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [Planos de sistema telefônico](https://go.microsoft.com/fwlink/?LinkId=799763)
    
Você também pode ver as informações conectando- [se ao centro de administração do Microsoft 365](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) e indo**fazer assinaturas de** >  **cobrança** > **adicionar assinaturas**.
  
Para ver uma tabela com as licenças ou licenças necessárias para cada recurso, consulte [Licenciamento de Complementos do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
  
## <a name="related-topics"></a>Tópicos relacionados

- [Instalar o Skype for Business Online](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [Configurar a Caixa Postal na Nuvem - Ajuda da administração](set-up-phone-system-voicemail.md)
    
- [Configurar Planos de Chamadas](set-up-calling-plans.md) e [Planos de Chamadas para o Office 365](calling-plans-for-office-365.md)
    
- [Adicionar fundos e gerenciar Créditos de Comunicação](add-funds-and-manage-communications-credits.md)
    
  
 
