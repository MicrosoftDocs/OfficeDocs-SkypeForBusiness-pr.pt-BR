---
title: Configurar a licença de Telefone de Área Comum para o Microsoft Teams
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
f1keywords: None
ms.custom:
- Phone System
description: 'Saiba como configurar telefones celulares comuns para "lobbies", áreas de recepção e salas de conferência '
ms.openlocfilehash: d00d91d4461a8b197f8629d3dfe9cee6653b2473
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925302"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a>Configurar a licença de Telefone de Área Comum para o Microsoft Teams
> [!NOTE]
> Telefones celulares comuns não oferecem suporte ao correio de voz.

Um telefone de área comum geralmente é colocado em uma área como um lobby ou outra área que está disponível para muitas pessoas fazer uma chamada; por exemplo, uma área de recepção, um lobby ou um telefone de conferência. Os telefones de área comuns são configurados como dispositivos, e não usuários, e podem entrar automaticamente em uma rede.

Nas etapas a seguir, ajudaremos você a configurar uma conta para o sistema telefônico implantar telefones de área comuns para a sua organização. Para obter uma experiência de reunião mais completa, incluindo videoconferência, considere comprar a licença de sala de reunião dedicada com um dispositivo de sala de reunião. 

As primeiras coisas que você precisa fazer são comprar uma licença de CAP (telefone fixo) comum e verificar se você tem um telefone certificado. Para procurar e saber mais sobre telefones certificados, acesse [dispositivos Microsoft Teams](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1). 

## <a name="step-1---buy-the-licenses"></a>Etapa 1 - Compre as licenças

1. No centro de administração do Microsoft 365, vá para**serviços de compra** de **cobrança** > e, em seguida, expanda **outros planos**.

    ![Captura de tela mostrando o bloco de telefone de área comum](media/set-up-common-area-phone-image1.png)

2. Selecione comprar **telefone** > da área comum**agora**.

3. Na página **check-out** , clique em **comprar agora**.

4. Expanda **assinaturas complementares** e clique para comprar um plano de chamadas. Escolha o **plano de chamadas domésticas** ou de **chamadas domésticas e internacionais**.

> [!NOTE]
> Você não precisa de uma licença do Sistema de Telefonia. Ela está incluída na licença do Telefone da Área Comum.

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

Para obter mais informações, consulte [Adicionar um usuário](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide).

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Etapa 3 - Atribuir um número de telefone à conta de usuário do Telefone de Área Comum

Use o centro de administração do Skype for Business para atribuir um número ao usuário.

1. No centro de administração do Microsoft 365, **selecione centros** > de administração e**equipes & portal do Skype** > **Legacy**.

2. No centro de administração do Skype for Business, selecione**números de telefone**de **voz** > .

3.  Selecione um número na lista de números de telefone e clique em **Atribuir**.

4. Na página **atribuir** , na caixa usuário de voz, digite o nome do usuário que usará o telefone e, em seguida, selecione o usuário na lista suspensa **selecionar um usuário de voz** .

5. Na página, você precisa adicionar um endereço de emergência. Escolha **Pesquisar por cidade**, **Pesquisar por descrição**ou **Pesquisar por local** na lista suspensa e, em seguida, insira a cidade, a descrição ou o local na caixa de texto. Depois de Pesquisar, procure em **selecionar endereço de emergência** para selecionar o endereço correto para você.

6. Clique em **Salvar** e seu usuário ficará assim:

   ![Captura de tela mostrando atribuição de licença](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> Os usuários só aparecerão se tiverem uma licença do sistema de telefonia aplicada. Quando fizer isso, pode levar um tempo para que o usuário apareça na lista.

Para obter mais informações, consulte [como obter números de telefone para seus usuários](/microsoftteams/getting-phone-numbers-for-your-users).

Você também pode levar seu número de telefone com outra transportadora e "portar" ou transferi-la para o Office 365. Veja [transferir números de telefone para o Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).


