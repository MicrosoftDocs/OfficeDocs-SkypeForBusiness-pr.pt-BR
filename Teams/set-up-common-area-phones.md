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
description: 'Saiba como configurar telefones de área comuns para lo lobbys, áreas de recepção e salas de conferência '
ms.openlocfilehash: f940ea7c14ad55c8cd3842e9830eb82da0d8867f
ms.sourcegitcommit: d7e0406276def8bc731aa6dcbd49802441ec5138
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2020
ms.locfileid: "48476706"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a>Configurar a licença de Telefone de Área Comum para o Microsoft Teams
> [!NOTE]
> Telefones de área comuns não são suportados pela caixa postal.

Um telefone de área comum normalmente é colocado em uma área como um lobby ou outra área que está disponível para muitas pessoas fazer uma chamada; por exemplo, uma área de recepção, lobby ou telefone de conferência. Telefones de área comuns estão entre com contas vinculadas a uma licença de Telefone de Área Comum. A política do TeamsIPPhone também deve ser adequadamente definida para que o telefone tenha uma experiência de usuário de área comum.

Nas etapas abaixo, ajudaremos você a configurar uma conta do Sistema de Telefonia para implantar telefones de área comuns para sua organização. Para obter uma experiência de sala de reunião mais completa, incluindo audioconferência, considere comprar a licença dedicada da Sala de Reunião com um dispositivo de sala de reunião. 

Primeiro, você precisa comprar uma licença de Telefone de Área Comum (CAP) e garantir que tenha um telefone certificado. Para pesquisar e saber mais sobre telefones certificados, vá para dispositivos [microsoft teams.](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1) 

## <a name="step-1---buy-the-licenses"></a>Etapa 1 - Compre as licenças

1. No Centro de administração do Microsoft 365, vá para Serviços **de** Compra de Cobrança e  >   expanda **Outros planos.**

    ![Captura de tela mostrando o tile Telefone de Área Comum](media/set-up-common-area-phone-image1.png)

2. Selecione **Comprar telefone de área** comum  >  **agora.**

3. Na página Check-out, clique **em Comprar agora.**

4. Expanda **assinaturas de complemento e** clique para comprar um Plano de Chamada. Escolha o Plano **de Chamada Doméstica** ou o Plano de Chamada Doméstica e **Internacional.**

> [!NOTE]
> Se você estiver usando o Roteamento Direto do Sistema de Telefonia do Microsoft Phone, não precisará de uma licença do Plano de Chamada.

> [!NOTE]
> Você não precisa adicionar uma licença do Sistema de Telefonia. Ela está incluída na licença do Telefone da Área Comum.

Para obter mais informações sobre licenças, consulte o licenciamento [de complementos do Microsoft Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)

A licença do Telefone de Área Comum dá suporte a: 


|   |  Telefone de Área Comum  |
|---------|---------|
|Skype for Business |   &#x2714; |
|Microsoft Teams |   &#x2714; |
|Sistema de Telefonia |    &#x2714; |
|Audioconferência |       &#x2718; &sup1;  |
|Microsoft Intune |    &#x2718; |
|Disponibilidade mundial |       &#x2718; &sup2;  |
|Disponibilidade do Canal |    EA, EAS, CSP, GCC, EES, Web Direct  |
|      |         |

&sup1; Os Telefones de Área Comuns podem ingressar em audioconferência por meio do número de discagem fornecido pelo organizador da reunião

&sup2; Não disponível em nuvens soberanas  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Etapa 2 - Criar uma nova conta de usuário para o telefone e atribuir as licenças

1. No Centro de administração do Microsoft 365, vá para **usuários**  >  **ativos**  >  **adicionarem um usuário.**

2. Insira um nome de usuário como "Principal" para o nome e "Recepção" para o segundo nome.

3. Insira um nome de exibição se ele não gerar automaticamente um, como "Recepção Principal".

4. Insira um nome de usuário, como "MainReception" ou "Mainlobby".

5. Para telefones de área comum, talvez você queira definir uma senha manualmente ou ter a mesma senha para todos os telefones de área comuns. Além disso, você pode pensar em limpar a caixa de seleção Fazer com que **este usuário altere** a senha ao entrar pela primeira vez.

6. Atribua as licenças ao usuário. Na mesma página, clique para expandir as **Licenças de produto**. A ligue o Telefone de Área Comum e escolha um Plano de Chamadas **Domésticas** ou um Plano **de Chamadas Domésticas e Internacionais.** 

    ![Captura de tela mostrando atribuição de licença](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> Se você estiver usando o Roteamento Direto do Sistema de Telefonia do Microsoft Phone, não será necessário atribuir uma licença de Plano de Chamada.

Para obter mais informações, consulte [Atribuir licenças aos usuários.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Etapa 3 - Atribuir um número de telefone à conta de usuário do Telefone de Área Comum

Use o Centro de administração do Teams para atribuir um número ao usuário.

1. No Centro de administração do Teams, selecione **números de telefone** de  >  **voz.**

3.    Selecione um número na lista de números de telefone e clique em **Atribuir**.

4. Na **página** Atribuir, na caixa Usuário de voz, digite o nome do usuário que estará  usando o telefone e selecione o usuário na lista de seleção Selecionar um usuário de voz.

5. Em seguida, você precisa adicionar um endereço de emergência. Escolha **Pesquisar por cidade,** Pesquisar  por descrição ou Pesquisar por local na listada e insira a cidade, a descrição ou o local na caixa de texto.  Depois de pesquisar, procure em **Selecionar endereço de emergência** para escolher o endereço certo para você.

6. Clique em **Salvar** e seu usuário ficará assim:

   ![Captura de tela mostrando atribuição de licença](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> Os usuários só aparecerão se eles têm uma licença do Sistema de Telefonia aplicada. Quando fizer isso, pode levar um tempo para que o usuário apareça na lista.

Para obter mais informações, consulte [Obter números de telefone para seus usuários.](getting-phone-numbers-for-your-users.md)

Você também pode pegar seu número de telefone que tem com outra operadora e "porta", ou transferi-lo para o Microsoft 365 ou o Office 365. Veja [Transferir números de telefone para o Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)
