---
title: Configurar a licença de telefone da área comum
ms.author: lolaj
author: LolaJacobsen
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
description: 'Saiba como configurar telefones celulares comuns para "lobbies", áreas de recepção e salas de conferência '
ms.openlocfilehash: da44a7d66cdc0810405711719f4545caf64007a7
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140864"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a>Configurar a licença de Telefone de Área Comum para o Microsoft Teams
> [!NOTE]
> Telefones celulares comuns não oferecem suporte ao correio de voz.

Um telefone de área comum geralmente é colocado em uma área como um lobby ou outra área que está disponível para muitas pessoas fazer uma chamada; por exemplo, uma área de recepção, um lobby ou um telefone de conferência. Os telefones de área comuns são configurados como dispositivos, e não usuários, e podem entrar automaticamente em uma rede.

Nas etapas a seguir, ajudaremos você a configurar uma conta para o sistema telefônico implantar telefones de área comuns para a sua organização. Para obter uma experiência de reunião mais completa, incluindo videoconferência, considere comprar a licença de sala de reunião dedicada com um dispositivo de sala de reunião. 

Primeiro, você precisa comprar uma licença de telefone (CAP) de área comum e verificar se tem um telefone certificado. Para procurar e saber mais sobre telefones certificados, acesse [dispositivos Microsoft Teams](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1). 

## <a name="step-1---buy-the-licenses"></a>Etapa 1 - Compre as licenças

1. No centro de administração do Microsoft 365, vá para**serviços de compra** de **cobrança** > e, em seguida, expanda **outros planos**.

    ![Captura de tela mostrando o bloco de telefone de área comum](media/set-up-common-area-phone-image1.png)

2. Selecione comprar **telefone** > da área comum**agora**.

3. Na página check-out, clique em **comprar agora**.

4. Expanda **assinaturas complementares** e clique para comprar um plano de chamadas. Escolha o **plano de chamadas domésticas** ou de **chamadas domésticas e internacionais**.

> [!NOTE]
> Se você estiver usando o roteamento direto do sistema de telefonia da Microsoft, você não precisa de uma licença de plano de chamada.

> [!NOTE]
> Você não precisa adicionar uma licença do sistema de telefone. Ela está incluída na licença do Telefone da Área Comum.

Para obter mais informações sobre licenças, consulte [Licenciamento de Complementos do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

A licença de telefonia do Common Area é compatível com: 


|   |  Telefone de Área Comum  |
|---------|---------|
|Skype for Business |   &#x2714; |
|Microsoft Teams |   &#x2714; |
|Sistemas de telefonia |    &#x2714; |
|Audioconferência |       &#x2718; &SUP1;  |
|Microsoft Intune |        &#x2718; &sup2; |
|Disponibilidade mundial |    &#x2714; |
|Disponibilidade do canal |    EA, EAS, CSP, GCC, EES, Web Direct  |
|      |         |

&SUP1; Os telefones da área comum podem ingressar em conferências de áudio por meio do número de discagem fornecido pelo organizador da reunião

&sup2; Não disponível em nuvens soberana  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Etapa 2 - Criar uma nova conta de usuário para o telefone e atribuir as licenças

1. No centro de administração do Microsoft 365, vá para **usuários** > usuários**ativos** > **Adicionar um usuário**.

2. Insira um nome de usuário como "Main" para o primeiro nome e "recepção" para o segundo nome.

3. Digite um nome para exibição se ele não gerar automaticamente uma como "recepção principal".

4. Digite um nome de usuário como "MainReception" ou "Mainlobby".

5. Para telefones celulares comuns, talvez você queira definir uma senha manualmente ou ter a mesma senha para todos os seus telefones comuns da área. Além disso, você pode pensar em desmarcar a caixa de seleção **fazer com que este usuário altere sua senha quando entrar pela primeira vez** .

6. Atribua as licenças ao usuário. Na mesma página, clique para expandir as **Licenças de produto**. Habilite o telefone de área comum e escolha um **plano de chamadas domésticas** ou um **plano de chamadas doméstico e internacional**. 

    ![Captura de tela mostrando atribuição de licença](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> Se você estiver usando o roteamento direto do sistema de telefonia da Microsoft, você não precisará atribuir uma licença de plano de chamada.

Para obter mais informações, consulte [Adicionar um usuário](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide).

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Etapa 3 - Atribuir um número de telefone à conta de usuário do Telefone de Área Comum

Use o centro de administração do teams para atribuir um número ao usuário.

1. No centro de administração do Teams, selecione**números de telefone**de **voz** > .

3.    Selecione um número na lista de números de telefone e clique em **Atribuir**.

4. Na página **atribuir** , na caixa usuário de voz, digite o nome do usuário que usará o telefone e, em seguida, selecione o usuário na lista suspensa **selecionar um usuário de voz** .

5. Em seguida, você precisa adicionar um endereço de emergência. Escolha **Pesquisar por cidade**, **Pesquisar por descrição**ou **Pesquisar por local** na lista suspensa e, em seguida, insira a cidade, a descrição ou o local na caixa de texto. Depois de Pesquisar, procure em **selecionar endereço de emergência** para selecionar o endereço correto para você.

6. Clique em **Salvar** e seu usuário ficará assim:

   ![Captura de tela mostrando atribuição de licença](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> Os usuários só aparecerão se tiverem uma licença do sistema de telefonia aplicada. Quando fizer isso, pode levar um tempo para que o usuário apareça na lista.

Para obter mais informações, consulte [como obter números de telefone para seus usuários](getting-phone-numbers-for-your-users.md).

Você também pode levar seu número de telefone com outra transportadora e "portar" ou transferi-la para o Office 365. Veja [transferir números de telefone para o Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).


