---
title: Pesquisar números de telefone para usuários
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: davlick, roykuntz, jastark
ms.topic: article
ms.assetid: cc22c49a-c644-4151-a2fc-a1474148f8ba
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Veja como pesquisar números de telefone que você pode atribuir aos usuários, por país ou região e cidade, e especifique a quantidade de números necessários.
ms.openlocfilehash: 46bdc54f892993b9a161690a5d42692fe66b9f5a
ms.sourcegitcommit: 4847f24e8c644336d2b2f48aa09e2cf91360e4dd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2022
ms.locfileid: "64686368"
---
# <a name="search-for-telephone-numbers-for-users"></a>Pesquisar números de telefone para usuários

Ao configurar usuários em sua organização para fazer e receber chamadas telefônicas usando números de telefone fornecidos pela Microsoft, primeiro você deve usar o centro de administração do Microsoft Teams e adquirir números de telefone para serem atribuídos **aos** usuários. O número de telefone que você atribui a um usuário será um número de telefone que você adquiriu anteriormente para sua organização; o número será listado na lista suspensa quando você editar as propriedades do usuário e clicar em **Atribuir**.
  
Antes de atribuir números de telefone fornecidos pela Microsoft aos usuários, você deve usar a página  Obter novos números para pesquisar números de telefone disponíveis para você. Você pode pesquisar por **País (Mercado)**, **Tipo de número** e **Local**. Em seguida, você verá uma lista de operadores que fornecem números nesse país.

Se você selecionar a Microsoft como sua operadora, poderá adquirir os números no centro de administração do Teams inserindo a quantidade de números de telefone necessários para seus usuários.A página limitará automaticamente a quantidade com base na quantidade que você ainda tem disponível para adquirir. Se você selecionar um Conexão do operador, será direcionado para a página de aterrissagem do operador selecionado para concluir a ordem de número.

A maneira como você adquire e gerencia números de telefone difere dependendo da opção de conectividade PSTN: Planos de Chamadas da Microsoft, Conexão do operador ou Roteamento Direto.

Este artigo se aplica aos [Planos de Chamadas da Microsoft](#search-for-telephone-numbers-for-microsoft-calling-plans) [e Conexão do operador](#search-for-telephone-numbers-for-operator-connect). Para obter mais informações sobre todas as opções, [consulte Gerenciar números de telefone para sua organização](/microsoftteams/manage-phone-numbers-landing-page).

## <a name="search-for-telephone-numbers-for-microsoft-calling-plans"></a>Pesquisar números de telefone para Planos de Chamadas da Microsoft

Para pesquisar números de telefone para seus usuários:
  
1. Vá para o **centro Microsoft Teams administrador.**

2. No painel de navegação esquerdo, **selecione Voz** >  **Telefone númerosGet** >  **novos números**.
  
    > [!IMPORTANT]
    > Para ver a opção Voz  no painel de navegação à esquerda no centro de administração do Teams, primeiro você deve comprar pelo menos uma licença **do Enterprise E5 ou E3**, uma licença de complemento do **Sistema de Telefonia** ou uma licença de complemento de Audioconferência.  

3. Na página **Selecionar local e quantidade** , selecione um local na lista suspensa **País (** Mercado).

4. Selecione **Usuário** na **lista suspensa Tipo** de número.

5. Dependendo do País (Mercado) que você selecionou, agora você terá opções diferentes disponíveis para usar para localizar os números de telefone necessários.  

6. Em **Quantidade**, insira o número de números de telefone desejados para sua organização e clique em **Avançar**. [!CUIDADO] Você tem 10 minutos para selecionar seus números de telefone. Se você demorar mais de 10 minutos, os números serão retornados ao pool de números de telefone.

    > [!NOTE]
    > Você pode ver o número de números de telefone disponíveis para você (que se baseia no número de licenças), listado ao lado de **Quantity**.
  
7. Na página **Obter números** , selecione os números de telefone desejados, clique em Adquirir **números** e clique em **Avançar**.

    > [!IMPORTANT]
    > Você pode adquirir mais números de telefone do que as licenças da Microsoft. Para determinar quantos números de telefone você pode adquirir, pegue seu número de licenças do Plano de Chamadas da Microsoft, adicione 10% do número de licenças, adicione 10 e remova quantas já tiver adquirido. Por exemplo, se você tiver 100 licenças de Plano de Chamadas Domésticas, Plano de Chamadas Internacionais e/ou Plano de Chamadas Domésticas e Internacionais **da Microsoft,** poderá reservar 120 números de telefone, supondo que ainda não tenha adquirido alguns números de telefone para esses 100 usuários. Para obter mais detalhes, [veja quantos números de telefone você pode obter?](./how-many-phone-numbers-can-you-get.md)

8. Na página **Confirmação** , verifique suas escolhas e clique em **Fazer pedido**.

9. Quando você retornar à página **de Telefone**, selecione o número de telefone ou números que deseja atribuir e clique em **Editar** para atribuí-lo a um usuário.

## <a name="search-for-telephone-numbers-for-operator-connect"></a>Procurar números de telefone para Conexão do operador

1. Vá para o **centro Microsoft Teams administrador.**

2. No painel de navegação esquerdo, **selecione Voz** >  **Telefone númerosGet** >  **novos números**.
  
    > [!IMPORTANT]
    > Para ver a opção Voz  no painel de navegação à esquerda no centro de administração do Teams, primeiro você deve comprar pelo menos uma licença **do Enterprise E5 ou E3**, uma licença de complemento do **Sistema de Telefonia** ou uma licença de complemento de Audioconferência.  

3. Na página **Selecionar local e quantidade** , selecione um local na lista suspensa **País (** Mercado).

4. Selecione **Usuário** na **lista suspensa Tipo** de número.

5. Dependendo do País (Mercado) que você selecionou, agora você terá opções diferentes disponíveis para usar para localizar os números de telefone necessários. Você pode filtrar para mostrar apenas os operadores que adicionou selecionando **Mostrar meus operadores**.

6. Se você já tiver fornecido consentimento para o operador, será direcionado para a página de aterrissagem do operador para concluir o processo de pedido.

7. Se você não tiver fornecido consentimento para o operador, será direcionado para habilitar o operador na página de operador escolhida no centro de Teams administrador. Para obter mais informações, consulte [Habilitar um operador](operator-connect-configure.md#enable-an-operator).

8. Depois que o pedido for concluído, o operador carregará números de telefone para seu locatário e você poderá atribuí-los aos usuários.  

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar números de telefone para sua organização](manage-phone-numbers-landing-page.md)

[Termos e condições para chamadas de emergência](./emergency-calling-terms-and-conditions.md)

[Rótulo de aviso de isenção de responsabilidade de Chamada de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
