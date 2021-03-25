---
title: Configurar a licença do Telefone de Área Comum
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/13/2018
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 'Saiba como configurar Telefones de Área Comum para lobbies, áreas de recepção e salas de conferência '
ms.openlocfilehash: bb17b21eac262c160abc3e16a4b552fb32b97d00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117109"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a>Configurar a licença de Telefone de Área Comum para o Microsoft Teams
> [!NOTE]
> Telefones de área comum não suportam caixa postal.

Um telefone de área comum normalmente é colocado em uma área como um lobby ou outra área que está disponível para muitas pessoas fazer uma chamada; por exemplo, uma área de recepção, lobby ou telefone de conferência. Telefones de área comum são assinados com contas vinculadas a uma licença de Telefone de Área Comum. A política TeamsIPPhone também deve ser adequadamente definida para que o telefone tenha uma experiência de usuário de área comum.

Nas etapas abaixo, ajudaremos você a configurar uma conta para o Sistema de Telefonia para implantar telefones de área comum para sua organização. Para obter uma experiência de sala de reunião mais completa, incluindo audioconferência, considere comprar a licença da Sala de Reunião dedicada com um dispositivo de sala de reunião. 

Primeiro, você precisa comprar uma licença de Telefone de Área Comum (CAP) e certificar-se de ter um telefone certificado. Para pesquisar e saber mais sobre telefones certificados, acesse dispositivos [do Microsoft Teams.](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1) 

## <a name="step-1---buy-the-licenses"></a>Etapa 1 - Compre as licenças

1. No Centro de administração do Microsoft 365, vá para **Serviços de** Compra de Cobrança e  >   **expanda Outros planos.**

    ![Captura de tela mostrando o tile Common Area Phone](media/set-up-common-area-phone-image1.png)

2. Selecione **Common Area Phone** Buy  >  **now**.

3. Na página Checkout, clique em **Comprar agora**.

4. Expanda **assinaturas de complemento e** clique para comprar um Plano de Chamada. Escolha o Plano **de Chamada Doméstica** ou o Plano de Chamada Doméstico e **Internacional.**

> [!NOTE]
> Se você estiver usando o Roteamento Direto do Sistema de Telefonia da Microsoft, não precisará de uma licença de Plano de Chamadas.

> [!NOTE]
> Você não precisa adicionar uma licença do Sistema de Telefonia. Ela está incluída na licença do Telefone da Área Comum.

Para obter mais informações sobre licenças, consulte [Licenciamento de complemento do Microsoft Teams.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

A licença Common Area Phone dá suporte a: 


|   |  Telefone de Área Comum  |
|---------|---------|
|Skype for Business |   &#x2714; |
|Microsoft Teams |   &#x2714; |
|Sistema de Telefonia |    &#x2714; |
|Audioconferência |       &#x2718; &sup1;  |
|Microsoft Intune |    &#x2718; |
|Disponibilidade Mundial |       &#x2718; &sup2;  |
|Disponibilidade do Canal |    EA, EAS, CSP, GCC, EES, Web Direct  |
|      |         |

&sup1; Os Telefones de Área Comum podem ingressar em conferências de áudio por meio do número de discagem fornecido pelo organizador da reunião

&sup2; Não disponível em nuvens soberanas  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Etapa 2 - Criar uma nova conta de usuário para o telefone e atribuir as licenças

1. No Centro de administração do Microsoft 365, vá para usuários  >  **ativos**  >  **adicionar um usuário**.

2. Insira um nome de usuário como "Main" para o primeiro nome e "Recepção" para o segundo nome.

3. Insira um nome de exibição se ele não gerar automaticamente um como "Recepção Principal".

4. Insira um nome de usuário como "MainReception" ou "Mainlobby".

5. Para telefones de área comum, talvez você queira definir uma senha manualmente ou ter a mesma senha para todos os telefones de área comum. Além disso, você pode pensar em limpar a caixa de seleção Fazer com que **esse usuário altere** a senha ao entrar pela primeira vez.

6. Atribua as licenças ao usuário. Na mesma página, clique para expandir as **Licenças de produto**. A turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a Domestic and International Calling **Plan**. 

    ![Captura de tela mostrando atribuição de licença](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> Se você estiver usando o Roteamento Direto do Sistema de Telefonia da Microsoft, não será necessário atribuir uma licença de Plano de Chamadas.

Para obter mais informações, [consulte Atribuir licenças aos usuários](/microsoft-365/admin/manage/assign-licenses-to-users).

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Etapa 3 - Atribuir um número de telefone à conta de usuário do Telefone de Área Comum

Use o centro de administração do Teams para atribuir um número ao usuário.

1. No centro de administração do Teams, selecione **Números de Telefone** de  >  **Voz**.

3.    Selecione um número na lista de números de telefone e clique em **Atribuir**.

4. Na página **Atribuir,** na caixa Usuário voz, digite o nome do usuário que estará usando  o telefone e selecione o usuário na listada Selecionar um usuário de voz.

5. Em seguida, você precisa adicionar um endereço de emergência. Escolha **Pesquisar por cidade,** **Pesquisar** por descrição ou Pesquisar por local na listada e insira a cidade, a descrição ou o local na caixa de texto.  Depois de pesquisar, procure em **Selecionar endereço de emergência** para escolher o endereço certo para você.

6. Clique em **Salvar** e seu usuário ficará assim:

   ![Captura de tela mostrando atribuição de licença](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> Os usuários só aparecerão se eles têm uma licença do Sistema de Telefonia aplicada. Quando fizer isso, pode levar um tempo para que o usuário apareça na lista.

Para obter mais informações, consulte [Obter números de telefone para seus usuários](getting-phone-numbers-for-your-users.md).

Você também pode levar seu número de telefone que você tem com outra operadora e "porta" ou transferi-lo para o Microsoft 365 ou Office 365. Consulte [Transferir números de telefone para o Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).