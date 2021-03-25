---
title: Configurar Créditos de comunicação da sua organização
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
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Licensing
- seo-marvel-apr2020
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: 98591d7603cdf63a76bef3478834f37504d8ff6c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117099"
---
# <a name="set-up-communications-credits-for-your-organization"></a>Configurar Créditos de comunicação da sua organização

Você precisará configurar Créditos de Comunicação se quiser usar números gratuitos com o Skype for Business e o Microsoft Teams. Além disso, recomendamos configurar créditos de comunicação para seus planos de chamada (domésticos ou internacionais) e usuários de Audioconferência que precisam da capacidade de discar para **qualquer destino**. Muitos países/regiões estão incluídos, mas alguns destinos podem não estar incluídos em seu Plano de Chamada ou assinaturas de Audioconferência. Se você não configurar a cobrança de Créditos de Comunicações e atribuir uma licença de **Créditos** de Comunicação aos usuários e ficar sem minutos para sua organização (dependendo do plano de chamada ou do plano de Audioconferência em seu país/região), esses usuários não poderão fazer chamadas ou discar em reuniões de Audioconferência. Você pode obter mais informações, incluindo valores de financiamento recomendados, lendo [O que são créditos de comunicação?](what-are-communications-credits.md)
  
> [!NOTE]
> Para descobrir quanto isso custa, [consulte as taxas aqui](https://go.microsoft.com/fwlink/p/?LinkId=799523 ). 
  
## <a name="step-1-assign-an-audio-conferencing-or-calling-plan-license-to-your-users"></a>Etapa 1: Atribuir uma licença de Audioconferência ou Plano de Chamada aos usuários

Ao se inscrever, você tem um determinado número de minutos, dependendo do seu país/região. Você pode pesquisar seu país ou região na lista de disponibilidade do país ou região para Planos de [Audioconferência](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md#select-your-country-or-region-to-see-whats-available-for-your-organization) e Chamada para ver o número de minutos que você receberá. Depois de usar esses minutos, as chamadas serão desconectadas. Para evitar que isso aconteça, você precisa configurar Créditos de Comunicação.
  
Para fazer isso, **você precisa atribuir uma licença de Audioconferência ou Sistema de Telefonia** aos seus usuários.
  
- Atribua **uma licença de Audioconferência** aos usuários. Consulte [Atribuir licenças de complemento do Microsoft Teams.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
    
    Depois de atribuir essa licença, você precisará configurar a audioconferência. Para obter instruções passo a passo, consulte [Try or purchase Audio Conferencing in Microsoft 365 or Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).
    
- Atribua **o Sistema de** Telefonia e uma licença do **Plano** de Chamadas Doméstico ou Doméstico e Internacional aos usuários. Consulte [Atribuir licenças de complemento do Microsoft Teams.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
    
    > [!NOTE]
    > Embora não seja necessário para Créditos de Comunicação, você  ainda precisa atribuir um Plano de Chamada Doméstica ou uma licença do Plano de Chamada Doméstico e **Internacional.**
  
    Após atribuir essas licenças, você deverá obter os números de telefone da sua organização e atribuí-los aos usuários. Para obter instruções passo a passo, consulte [Configurar Planos de Chamada](set-up-calling-plans.md).
    
Para obter mais informações, consulte [Licenciamento de complementos do Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a>Etapa 2: Configurar créditos de comunicações para sua organização

1. Entre no Centro de administração do [Microsoft 365](https://portal.office.com/Adminportal) com sua conta de trabalho ou de estudante.
    
2. Na navegação à esquerda do Centro de administração do Microsoft 365, vá para **Cobrança**  >  **de Serviços de Compra.** Role para baixo e selecione **Complementos**.

3. Selecione **Créditos de Comunicação**.
    
4. Na página **assinatura Créditos de** Comunicação, preencha suas informações e clique em **Próximo**:
    
   - **Adicionar fundos** Insira o valor que você deseja adicionar à sua conta. Se você não habilitar a recarga automática, depois que esses fundos são esgotados, os recursos de chamada habilitados usando Créditos de Comunicação serão interrompidos (como o serviço de chamada gratuita de entrada). Para evitar a reposição manual do saldo de Créditos de Comunicações sempre que o saldo atingir 0 (zero), recomendamos que você habilita o recurso de recarga automática.
    
   - **Recarga automática** A habilitação da recarga automática recarregará sua conta automaticamente quando o saldo ficar abaixo do limite definido.
    
     É recomendável que você use a **configuração** de Recarga Automática para evitar qualquer interrupção do serviço caso o saldo de Créditos de Comunicação atinja 0 (zero). Você receberá um email quando as transações de recarga for bem-sucedidas, quando as transações de recarga falharem (como um cartão de crédito expirado) e quando o saldo de Créditos de Comunicação atingir 0 (zero).
    
   - **Quantidade de recarga** Insira o valor na caixa **Recarregar com** que você deseja adicionar à sua conta depois que ele atingir a quantidade de gatilho abaixo.
    
   - **Quantidade de gatilho** Insira a quantidade em **Quando o saldo ficar abaixo** da caixa que será usada para ' *disparar*  ' a recarga automática. Quando o saldo ficar abaixo desse valor, o valor da recarga será adicionado automaticamente à sua conta.

      > [!NOTE]
     > Os fundos serão aplicados somente aos Créditos de Comunicação às taxas publicadas da Microsoft quando os serviços são usados. Os fundos não usados no prazo de 12 meses a contar da data de compra expirarão e serão cancelados. 
     > 
     > A cobrança mensal de Créditos de Comunicação só será aplicada se o fundo alloted tiver sido usado, para saber como verificar seu uso mensal, leia Relatório de uso do [PSTN](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) do Skype for Business
    
5. Insira suas informações de pagamento e clique em **Fazer pedido**.
    >[!IMPORTANT]
    >Se você for um cliente de licenciamento por volume, você pode escolher seu número enterprise agreement para pagamento. Se você tiver vários números enterprise agreement, você pode escolher qual prefere usar para o pagamento. Você também poderá especificar um número de ordem de compra que será associado ao número do enterprise agreement (se aplicável).
    
Cada organização terá um uso diferente de volume e taxas do Plano de Chamada a considerar. You will need to get this type of usage data from your current service provider. As organizações que já usam o Skype for Business Online como provedor de serviços podem obter dados de uso revisá-los no relatório de detalhes de uso do  >    >  **PSTN** do Centro de administração do Microsoft Teams.
  
Ao configurar os Créditos de Comunicação, você precisará investigar o uso de chamada para sua organização para determinar os valores necessários. Você pode obter informações de uso de chamadas examinando o relatório **Detalhes de uso de PSTN**. Este relatório permite exportar os registros de dados de chamada para o Excel se precisar armazenar os dados ou criar relatórios personalizados. Para saber como ver o uso, leia o relatório de uso [PSTN](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report).
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a>Etapa 3: Atribuir uma licença de Créditos de Comunicação aos usuários

1. Entre no Centro de administração do [Microsoft 365](https://portal.office.com/Adminportal) com sua conta de trabalho ou de estudante.
    
2. Na navegação à esquerda do Centro de administração do Microsoft 365, vá para **Usuários**  >  **Usuários ativos** e selecione um usuário na lista.
    
3. Escolha **Licenças e Aplicativos**.
    
4. Alterne **créditos de comunicações** **para On** para atribuir essa licença e selecione **Salvar**.
    
    > [!NOTE]
    > Mesmo que você tenha usuários que tenham uma licença **enterprise E5,** ainda é recomendável que você faça isso.

    > [!TIP]
    > Você pode usar o [Powershell](/powershell/module/skype/?view=skype-ps) para atribuir licenças e aplicativos a vários usuários com um comando.
  
## <a name="want-to-know-about-plans-and-pricing"></a>Quer saber mais sobre planos e preços?

Você pode ver os planos e os preços visitando um dos seguintes links:
  
- [Planos de Chamadas](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [Planos de Audioconferência](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [Planos do Sistema de Telefonia](https://go.microsoft.com/fwlink/?LinkId=799763)
    
Você também pode ver informações ao entrar no Centro de administração do [Microsoft 365](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) e ir para **Cobrança**  >  **de Assinaturas**  >  **Adicionar assinaturas**.
  
Para ver uma tabela com a licença ou licenças que você precisará para cada recurso, consulte [Licenciamento de complemento do Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
  
## <a name="related-topics"></a>Tópicos relacionados

- [Instalar o Skype for Business Online](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [Configurar a Caixa Postal na Nuvem - Ajuda da administração](set-up-phone-system-voicemail.md)
    
- [Configurar planos de chamada e](set-up-calling-plans.md) planos de chamada para o Microsoft [365 ou Office 365](calling-plans-for-office-365.md)
    
- [Adicionar fundos e gerenciar Créditos de Comunicação](add-funds-and-manage-communications-credits.md)
    
  
