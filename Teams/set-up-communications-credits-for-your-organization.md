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
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: e759fe9981728c97914c271dba69bfca6aebdd2b
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2019
ms.locfileid: "33632246"
---
# <a name="set-up-communications-credits-for-your-organization"></a>Configurar Créditos de Comunicação para sua organização

Você precisará configurar Créditos de Comunicação se quiser usar números gratuitos com o Skype for Business e o Microsoft Teams. Além disso, é recomendável que você configure créditos de comunicações para seus planos de chamada (doméstico ou internacional) e audioconferências usuários que precisam ter a capacidade de discar para **qualquer destino**. Muitos países/regiões são incluídos, mas alguns destinos não podem ser incluídos em suas assinaturas chamar planejar ou conferência de áudio. Se você não configurar créditos de comunicação de cobrança e atribuir uma licença **Créditos de comunicações** para seus usuários e executar check-out de minutos para sua organização (dependendo do seu plano de chamada ou conferência de áudio plano em seu país/região), esses usuários não será possível fazer chamadas ou discar a partir de reuniões de conferência de áudio. Você pode obter mais informações, incluindo recomendado, as quantidades de financiamento lendo [Cite Communications créditos?](what-are-communications-credits.md)
  
> [!NOTE]
> Para descobrir quanto isso custa, [consulte as taxas aqui](https://go.microsoft.com/fwlink/p/?LinkId=799523 ). 
  
## <a name="step-1-assign-an-audio-conferencing-and-calling-plan-license-to-your-users"></a>Etapa 1: Atribuir uma licença de conferência de áudio e chamar planejar para seus usuários

Quando você entrar, você obtém um determinado número de minutos dependendo do seu país/região. Você pode ver o número de minutos, você receberá a pesquisa para o país ou região [aqui](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). Depois de usar esses minutos, as chamadas serão desconectadas. Para evitar que isso aconteça, você precisará configurar créditos de comunicações.
  
Para fazer isso, **você precisa atribuir uma conferência de áudio ou uma licença de sistema telefônico** para seus usuários.
  
- Atribua uma licença de **Conferência de áudio** para seus usuários. Consulte [as equipes da Microsoft atribuir licenças](assign-teams-licenses.md).
    
    Depois de atribuir essa licença, você precisará configurar serviços de audioconferência. Para obter instruções detalhadas, consulte [tente ou adquirir audioconferência no Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).
    
- Atribua o **Sistema telefônico** e uma licença de chamar planejar local ou nacionais e internacional para seus usuários. Consulte [as equipes da Microsoft atribuir licenças](assign-teams-licenses.md).
    
    > [!NOTE]
    > Embora não é obrigatório para créditos de comunicações, você ainda precisará também atribuir um **Domésticas chamar planejar** ou uma licença **nacionais e internacionais chamar planejar** .
  
    Após atribuir essas licenças, você deverá obter os números de telefone da sua organização e atribuí-los aos usuários. Para obter instruções detalhadas, consulte [Configurar planos de chamada](set-up-calling-plans.md).
    
Para obter mais informações, consulte [Licenciamento de complemento de equipes da Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a>Etapa 2: Configurar os créditos de comunicações para sua organização

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. No painel de navegação à esquerda do Centro de administração do Microsoft 365, vá para **faturamento** > **assinaturas** > **Adicionar assinaturas**.

3. Expanda **inscrições de complemento**e escolha **Communications créditos** > **Compre agora**.
    
4. Na página de inscrição **Créditos de comunicações** , preencha as informações e clique em **Avançar**:
    
   - **Adicionar fundos** Insira o valor que você deseja adicionar à sua conta. Se você não habilitar o autocarga, depois que essas fundos são esgotados, recursos que são habilitados usando comunicações créditos de chamada será interrompida (por exemplo, o serviço de chamada gratuito entrado). Para evitar ter que alimentar manualmente seu saldo créditos de comunicações de cada vez que sua proporção atinge 0 (zero), é recomendável que você habilita o recurso de autocarga.
    
   - **Recarga automática** A habilitação da recarga automática recarregará sua conta automaticamente quando o saldo ficar abaixo do limite definido.
    
     É recomendável que você use a configuração de **Autocarga** para evitar qualquer interrupção do serviço deve seu saldo Communications créditos atingir 0 (zero). Você será enviado um email quando as transações de carga tiver êxito, quando as transações de carga falham (por exemplo, um cartão de crédito expirado) e quando seu saldo Communications créditos atinge 0 (zero).
    
   - **Recarregar a quantidade** Insira o valor na caixa **recarregar com** ser adicionada à sua conta, uma vez que ele atinge a quantidade de gatilho abaixo.
    
   - **Quantidade de gatilho** Insira o valor na caixa **quando o equilíbrio fica abaixo** que será usada ao ' *gatilho* ' a carga de automático. Depois que o seu saldo cair abaixo deste valor, a quantidade de carga será adicionada automaticamente à sua conta.

      > [!NOTE]
     > Fundos serão aplicados somente ao Communications créditos na Microsoft publicado taxas quando os serviços são usados. Os fundos não usados no prazo de 12 meses a contar da data de compra expirarão e serão cancelados. 
     > 
     > Cobrança mensal para comunicação créditos só será aplicado se tiver sido usado o fundo alocados para saber como verificar seu uso mensal, leia [Skype para relatório de uso de PSTN de negócios](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)
    
5. Insira suas informações de pagamento e clique em **Fazer pedido**.
    >[!IMPORTANT]
    >Se você for um cliente de licenciamento por volume, você pode escolher seu número enterprise agreement para pagamento. Se você tiver vários números enterprise agreement, você pode escolher qual prefere usar para o pagamento. Você também poderá especificar um número de ordem de compra que será associado ao número do enterprise agreement (se aplicável).
    
Cada organização terá o uso de diferente do volume de chamada planejar e taxas a serem considerados. You will need to get this type of usage data from your current service provider. As organizações que já usam Skype para Business Online já como seu provedor de serviços podem obter dados de uso, revisá-lo do **Skype para centro de administração de negócios** > **relatórios** > relatório de**detalhes de uso do PSTN** .
  
Quando você estiver configurando créditos de comunicações, você precisará investigue o uso de chamada para sua organização determinar os valores que você precisa. Você pode obter informações de uso de chamadas examinando o relatório **Detalhes de uso de PSTN**. Este relatório permite exportar os registros de dados de chamadas para o Excel, se você precisar armazenar os dados ou criar relatórios personalizados. Para saber como ver o uso, leia [Skype para relatório de uso de PSTN de negócios](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report).
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a>Etapa 3: Atribuir uma licença de comunicações créditos aos usuários

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. No painel de navegação à esquerda do Centro de administração do Microsoft 365, vá para **usuários** > **usuários ativos**e selecione um ou mais usuários da lista.
    
3. No painel Ação em **Licenças de**, clique em **Editar**.
    
4. Na página **licenças do produto** , alternar **Créditos de comunicações** para **em** para atribuir essa licença e clique em **Salvar**.
    
    > [!NOTE]
    > Mesmo se você tiver usuários que receberem uma licença **Enterprise E5** , ainda é recomendado que você faça isso.
  
## <a name="want-to-know-about-plans-and-pricing"></a>Quer saber mais sobre planos e preços?

Você pode ver os planos e preços do visitando um dos seguintes links:
  
- [Planos de chamadas](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [Planos de serviços de audioconferência](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [Planos de sistema de telefone](https://go.microsoft.com/fwlink/?LinkId=799763)
    
Você também pode ver informações entrando [no Centro de administração do Microsoft 365](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) e pretende **faturamento** > **assinaturas** > **Adicionar assinaturas**.
  
Para ver uma tabela com a licença ou licenças que são necessárias para cada recurso, consulte [Licenciamento de complemento de equipes da Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
  
## <a name="related-topics"></a>Tópicos relacionados

- [Instalar o Skype for Business Online](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [Configurar a Caixa Postal na Nuvem - Ajuda da administração](set-up-phone-system-voicemail.md)
    
- [Configurar Planos de Chamadas](set-up-calling-plans.md) e [Planos de Chamadas para o Office 365](calling-plans-for-office-365.md)
    
- [Adicionar fundos e gerenciar Créditos de Comunicação](add-funds-and-manage-communications-credits.md)
    
  
 
