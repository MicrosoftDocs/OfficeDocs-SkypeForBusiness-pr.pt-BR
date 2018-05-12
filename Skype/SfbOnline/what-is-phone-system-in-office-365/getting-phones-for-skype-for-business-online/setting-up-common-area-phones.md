---
title: Configurar telefones de área comum
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Conheça as etapas de implantação para obter o firmware correto, atualizá-la, se necessário, atribuir licenças e definir configurações para telefones de área comum.
ms.openlocfilehash: bcf7d8eaf287af0b801168c62e7c22915f735aa2
ms.sourcegitcommit: 6b868f683e1f2354eb42fdf33911e77b7a3a83e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2018
---
# <a name="set-up-common-area-phones"></a>Configurar telefones de área comum
Um telefone de área comum (COBRIR) geralmente é colocado em uma área como um lobby ou outra área que está disponível para muitas pessoas. Por exemplo, um telefone de área de recepção, porta telefone ou sala de reunião telefone, maiusculas são configuradas como dispositivos em vez de usuários e entrar automaticamente em uma rede. Nas etapas abaixo, podemos ajudá-lo a configurar uma conta para o sistema telefônico com planos de chamada para que você possa implantar esses tipos de telefones para sua organização.

## <a name="prerequisites-for-common-area-phones"></a>Pré-requisitos para telefones de área comum

A primeira coisa que você precisa fazer é confirmar que você tem o seguinte:

 - Adquirir a licença de telefone de área comum e um plano de chamada.
 - Pesquisar e comprar telefones aprovadas (exibir a lista [aqui](deploying-skype-for-business-online-phones.md)).         
 - Atualize o firmware em seus telefones (consulte suportada firmware [neste tópico](getting-phones-for-skype-for-business-online.md).  Você pode verificar o firmware no telefone você ao fazer isso:       
    - **Telefones Polycom VVX**: acesse **configurações** > **Status** > **plataforma** > **aplicativo** > **principal**.
    - **Telefones Yealink**: Ir para **Status** na tela do telefone principal.
    - **Telefones AudioCodes**: vá para o **Menu** > **Status do dispositivo** > **versão de Firmware** na tela de início. 
    - **Telefones de edição de telefone do Lync (LPE)**: vá para o **Menu** > **Informações do sistema** , na tela de início.

    As atualizações de firmware são gerenciadas pelo Serviço do Skype for Business. Todo firmware de telefone certificado pelo Skype for Business é carregado para o servidor de atualização do Skype for Business e a atualização do dispositivo é habilitada em todos os telefones por padrão. 

    Dependendo do tempo de inatividade no telefone e nos intervalos de sondagem, os telefones baixarão e instalarão automaticamente os builds certificados mais recentes. Você pode desabilitar as configurações de atualização de dispositivo usando o cmdlet [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) e definindo o parâmetro *EnableDeviceUpdate* para `false`.

## <a name="setting-up-a-common-area-phone"></a>Configurando um telefone de área comum
Você precisará devem seguir estas etapas:

### <a name="set-up-your-user-account-for-the-phone"></a>Configurar sua conta de usuário para o telefone

#### <a name="step-1---buy-the-licenses"></a>Etapa 1 - adquirir as licenças
1. No Centro de administração do Office 365, vá para **faturamento** > **Serviços de compra**, e adicionar **outros planos**.

    ![COBRIR-license.png](../../images/cap-license.png)
2. Clique no **Telefone de área comum** > **Compre agora** > no clique página **check-out** em **Compre agora**.
3. Clique em expandir **inscrições de complemento** e clique em comprar um plano de chamar. Escolha a **domésticas chamar plano** ou **plano de chamada nacionais e internacional**.

> [!Note]
> Você não precisa de uma licença de sistema telefônico. Ele tiver incluído com a licença do **Telefone de área comum** .

Para obter mais informações sobre licenças, consulte [Skype para licenciamento de complemento de negócios e equipes da Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

#### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Etapa 2 - criar uma nova conta de usuário para o telefone e atribuir licenças
1. No Centro de administração do Office 365, vá para **usuários** > **Usuários ativos** > **Adicionar um usuário**.
2. Coloque um **nome de usuário** , como "Main" para o primeiro nome e "Recepção" para o segundo nome.
3. Colocar um **nome para exibição** , se ele não gerar automaticamente um como "Main recepção".
4. Colocar um **nome de usuário** , como "MainReception" ou "Mainlobby".
5. Para telefones de área comum, talvez você queira definir uma senha manualmente ou ter a mesma senha para todos os telefones de área comum. Além disso, você pode achar sobre unselecting **tornar este usuário alterar suas senhas quando eles entrarem pela primeira vez**.

    > [!Tip]
    > AGUARDE!! Não clique em **Adicionar**!! Ah, se você clicou em **Add** o fazer isso: Centro de administração do Office 365 > **usuários** > **usuários ativos** e, em seguida, localizar o usuário. Na página de propriedades do usuário, clique em **licenças do produto** e clique em **Editar**. Na página **licenças do produto** , ligue o **Telefone de área comum** e escolher um **Domésticas chamar planejar** ou um doméstico e **Internacional chamar planejar**.

6. Se você ainda está lá, atribua as licenças para esse usuário. Na mesma página, clique para expandir a **licenças de produto**. Ative o seguinte:
    - Telefone de área comum
    - Em seguida, você precisará selecionar um **Domésticas chamar planejar** ou um doméstico e **Internacional chamar planejar**.
     
    Atribuir as licenças terá a seguinte aparência:

    ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

    > [!Note]
    > Para que você sabe, Skype para negócios plano 2 está incluído com a licença do **Telefone de área comum** .

Para obter mais detalhes, consulte [Adicionar um usuário](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).

#### <a name="step-3---assign-a-phone-number-to-the-user"></a>Etapa 3 - atribuir um número de telefone ao usuário
![logotipo-sfb-30x30.png](../../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**
1. No Centro de administração do Office 365 > **Admin centrais** > **Skype para negócios**.
2. No **Skype para centro de administração de negócios** >  **voz** > **números de telefone**.
3. Selecione um número da lista de números de telefone e clique em **atribuir**.
4. Na página **atribuir** , na caixa **usuário de voz** , digite o nome do usuário que é usado para o telefone, então, selecione o usuário em **Selecione um usuário de voz** a lista suspensa. 
5. Enquanto estiver na página, você precisará adicionar um endereço de emergência. Depois que você pode pesquisar, procure sob o **Selecione endereço de emergência** para escolher o certo para você.
6. Clique em **Salvar** e o usuário deve se parecer com isso:

    ![cobrir-usuário-number.png](../../images/cap-user-number.png)

   > [!Note]
   > Os usuários serão exibidas apenas se eles têm uma licença de **Sistema telefônico** aplicada. Se você acabou de fazer isso, em seguida, em alguns casos, levará um pouco para o usuário seja mostrada na lista.

Para mais informações, consulte [Getting números de telefone para seus usuários](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).

Se você está se perguntando, você também pode tirar seu número de telefone que você tenha com outra operadora e "*porta*" ou transferi-los em para o Office 365. Consulte, [transferir os números de telefone para o Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).

## <a name="step-4---setting-up-your-phone"></a>Etapa 4 - Configurando seu telefone

**Definindo o modo em um telefone**

O telefone ou telefones que você tiver devem ter ativado o modo de telefone de área comum. Você talvez queira verificação de que para certificar-se de que eles fazem. 

**Aqui está um exemplo de como configurar um telefone Polycom VVX**

- Habilite o modo de telefone de área comum para o VVX Polycom seguindo estas etapas:
    1. No seu navegador, conecte-se para a interface da web para que você pode ativar o modo de COBRIR.
    2. Vá para **configuração** e na opção **Skype para configuração de negócios** , selecione o **Telefone de área comum**.
    3. Clique em **Sim** para salvar as configurações.

- Agora que o modo de COBRIR estiver habilitado, configure o telefone usando a exibição do telefone. A exibição deve mostrar **CaAP está habilitado**. Em seguida, faça o seguinte:

    1. Clique em **configurações**.
    2. Selecione **Avançado**.
    3. Insira a senha.
    4. Nas **configurações de administração**, selecione **Configurações de telefone de área comum**.
    5. Habilite **COBRIR** e **modo COBRIR Admin**.
    6. Clique em **Salvar o arquivo Config**.

- Okey, agora o telefone estiver pronto para que possa entrar na tela inicial.

    1. Entrar, selecionando **configurações** > **recursos** > **Skype for Business.**
    2. Selecione **As credenciais do usuário**e selecione **entrar na web (COBRIR)** para gerar um código.
    3. Vá para o [portal de provisionamento](http://aka.ms/skypecap)e entrar como **administrador**.
    4. Insira o nome de exibição (por exemplo, Main recepção).

       > [!Note]
       > Se a **pesquisa para telefones de área comum só** está selecionada, desmarque a caixa de seleção e pesquisar novamente.'

    5. Na janela de código de emparelhamento, insira o código exibido no telefone e clique em **fornecimento**.

        Após essa última etapa, o telefone deve entrar automaticamente.

### <a name="related-topics"></a>Tópicos relacionados

- Saiba mais sobre os telefones disponíveis em [Implantando Skype para telefones Business Online](deploying-skype-for-business-online-phones.md).
- [Obter telefones para o Skype for Business Online](getting-phones-for-skype-for-business-online.md)


