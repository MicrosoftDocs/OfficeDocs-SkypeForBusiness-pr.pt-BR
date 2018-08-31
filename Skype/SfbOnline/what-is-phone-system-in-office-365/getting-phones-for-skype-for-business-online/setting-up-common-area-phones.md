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
ms.openlocfilehash: cb6cf1ed66f07ba618c74a47bc2c435229b235ec
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23779208"
---
# <a name="set-up-common-area-phones"></a>Configurar telefones de área comum
Um CAP (telefone de área comum) é normalmente colocado em áreas como saguões ou outras áreas disponíveis para muitas pessoas. Por exemplo, telefones de áreas de recepção, interfones ou telefones de salas de reunião, os CAPs são configurados como dispositivos em vez de usuários e se conectam automaticamente a uma rede. Nas etapas a seguir, ajudaremos você a configurar uma conta para o Sistema de Telefonia com planos de chamada, de modo que você possa implantar esses tipos de telefones na sua organização.

## <a name="prerequisites-for-common-area-phones"></a>Pré-requisitos para telefones de área comum

A primeira coisa a ser feita é confirmar que você já:

 - Comprou a licença do Telefone de Área Comum e um Plano de Chamadas.
 - Pesquisou e comprou telefones aprovados (veja a lista [aqui](deploying-skype-for-business-online-phones.md)).
 - Atualizou o firmware em seus telefones (veja o firmware suportado [neste tópico](getting-phones-for-skype-for-business-online.md)).  Você pode verificar o firmware do seu telefone da seguinte forma:
    - **Telefones Polycom VVX**: acesse **configurações** > **Status** > **plataforma** > **aplicativo** > **principal**.
    - **Telefones Yealink**: Ir para **Status** na tela do telefone principal.
    - **Telefones AudioCodes**: vá para o **Menu** > **Status do dispositivo** > **versão de Firmware** na tela de início.
    - **Telefones de edição de telefone do Lync (LPE)**: vá para o **Menu** > **Informações do sistema** , na tela de início.

    As atualizações de firmware são gerenciadas pelo Serviço do Skype for Business. Todo firmware de telefone certificado pelo Skype for Business é carregado para o servidor de atualização do Skype for Business e a atualização do dispositivo é habilitada em todos os telefones por padrão.

    Dependendo do tempo de inatividade no telefone e nos intervalos de sondagem, os telefones baixarão e instalarão automaticamente os builds certificados mais recentes. Você pode desabilitar as configurações de atualização de dispositivo usando o cmdlet [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) e definindo o parâmetro *EnableDeviceUpdate* para `false`.

## <a name="setting-up-a-common-area-phone"></a>Configuração de um telefone de área comum
Você precisará seguir estas etapas:

### <a name="step-1---buy-the-licenses"></a>Etapa 1 - Compre as licenças
1. No centro de administração do Office 365, acesse **Faturamento** > **Serviços de compra** e adicione **Outros planos**.

    ![CAP-license.png](../../images/cap-license.png)
2. Clique em **Telefone de Área Comum** > **Comprar agora** > na página **Finalizar compra** clique em **Comprar agora**.
3. Clique em expandir **Assinaturas de complementos** e depois clique em comprar um Plano de Chamadas. Escolha a **domésticas chamar plano** ou **plano de chamada nacionais e internacional**.

> [!Note]
> Você não precisa de uma licença do Sistema de Telefonia. Ela está incluída na licença do **Telefone da Área Comum**.

Para mais informações sobre licenças, veja [Licenciamento de complementos do Skype for Business e Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Etapa 2 - Criar uma nova conta de usuário para o telefone e atribuir as licenças
1. No centro de administração do Office 365, acesse **Usuários** > **Usuários Ativos** > **Adicionar um usuário**.
2. Coloque um **Nome de usuário** como "Principal" para o primeiro nome e "Recepção" para o segundo nome.
3. Coloque um **Nome para exibição** se "Recepção Principal"não for gerado automaticamente.
4. Coloque um **Nome de usuário** como "RecepçãoPrincipal" ou "LobbyPrincipal".
5. Para telefones de área comum, você pode definir uma senha manualmente ou usar a mesma senha para todos os telefones. Além disso, você pode desmarcar **Fazer com que esse usuário mude a senha quando entrar pela primeira vez**.

    > [!Tip]
    > ESPERE!! Não clique em **Adicionar**!! Se você clicou em **Adicionar**, faça isto: acesse o Centro de administração do Office 365 > **Usuários** > **Usuários ativos** e encontre o usuário. Em seguida, na página de propriedades do usuário, clique em **Licenças de produtos** e em **Editar**. Na página **Licenças de produtos**, ative **Telefone de Área Comum** e escolha um **Plano de Chamadas Domésticas** ou um **Plano de Chamadas Domésticas e Internacionais**.

6. Se você ainda estiver nessa página, atribua as licenças a esse usuário. Na mesma página, clique para expandir as **Licenças de produto**. Ative o seguinte:
    - Telefone de Área Comum
    - Você precisa escolher um **Plano de Chamadas Domésticas** ou um **Plano de Chamadas Domésticas e Internacionais**.

    A atribuição das licenças ficará assim:

    ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

    > [!Note]
    > Só para você saber, o Skype for Business Plan 2 está incluído na licença do **Telefone de Área Comum**.

Para mais detalhes, veja [Adicionar um usuário](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Etapa 3 - Atribuir um número de telefone à conta de usuário do Telefone de Área Comum

![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png)  Atribua um número de telefone ao usuário usando o ** Centro de administração do Skype for Business**

1. No Centro de administração do Office 365 > **Admin centrais** > **Skype para negócios**.
2. No **Centro de administração do Skype for Business** >  **Voz** > **Números de telefone**.
3. Selecione um número na lista de números de telefone e clique em **Atribuir**.
4. Na página **Atribuir**, na caixa **Usuário de voz** digite o nome do usuário usado para o telefone e, em seguida, selecione o usuário no menu suspenso **Selecionar um usuário de voz**.
5. Na página, você precisa adicionar um endereço de emergência. Depois de pesquisar, acesse **Selecionar endereço de emergência** para escolher o endereço certo para você.
6. Clique em **Salvar** e seu usuário ficará assim:

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > Os usuários só aparecerão se tiverem uma licença do **Sistema de Telefonia** aplicada. Quando fizer isso, pode levar um tempo para que o usuário apareça na lista.

Para mais detalhes, veja [Obtenção de números de telefone para seus usuários](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).

Se você está se perguntando, também é possível usar o número de telefone de outra operadora e "*fazer a portabilidade*" ou transferi-lo para o Office 365. Consulte, [transferir os números de telefone para o Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).

### <a name="step-4---setting-up-your-phone"></a>Etapa 4 - Configurar seu telefone

**Configuração do modo em um telefone**

O telefone ou telefones que você possui devem ter o **Modo de Telefone de Área Comum** ligado. É melhor conferir para ver se está tudo certo.

**Veja um exemplo de como configurar um telefone Polycom VVX**

- Habilite o modo Telefone de Área Comum para o Polycom VVX seguindo estas etapas:
    1. No seu navegador, conecte-se à interface da Web para habilitar o modo CAP.
    2. Depois acesse **Configuração** e na opção **Configuração do Skype for Business**, selecione **Telefone de Área Comum**.
    3. Clique em **Sim** para salvar suas configurações.

- Agora que o modo CAP está habilitado, configure o telefone usando o vídeo do telefone. O vídeo deve mostrar que **o CaAP está habilitado**. Em seguida, faça o seguinte:

    1. Clique em **Configurações**.
    2. Selecione **Avançado**.
    3. Insira a senha.
    4. Em **Configurações de administração**, selecione **Configurações do Telefone de Área Comum**.
    5. Habilite o **CAP** e o **Modo de Administração do CAP**.
    6. Clique em **Salvar configurações**.

- Agora seu telefone está pronto para que você possa entrar na tela inicial.

    1. Entre selecionando **Configurações** > **Recursos** > **Skype for Business.**
    2. Selecione **Credenciais do usuário**e depois **Entrada na Web (CAP)** para gerar um código.
    3. Acesse o [portal de configuração](https://aka.ms/skypecap) e entre como **administrador**.
    4. Insira o nome de exibição (p. ex., Recepção Principal).

       > [!Note]
       > Se a caixa de seleção **Pesquisar apenas Telefones de Área Comum** estiver marcada, desmarque e pesquise novamente.

    5. Na janela de código de pareamento, insira o código exibido no telefone e clique em **Provisão**.

        Após essa última etapa, é possível entrar automaticamente.


> [!NOTE]
> O site de configuração do CAP informa que ele redefinirá a senha da conta CAP para uma senha aleatória. Observe que a conta à qual o CAP está se referindo é a conta do Active Directory do Azure (AAD). Se você criou a conta somente no AAD, então o processo é direto. Se você tiver sincronizado um Active Directory local para o AAD, anote as credenciais que estiver usando e que serão alteradas pela configuração do CAP.


### <a name="related-topics"></a>Tópicos relacionados

- Saiba mais sobre os telefones disponíveis em [Implantação de telefones do Skype for Business Online](deploying-skype-for-business-online-phones.md).
- [Obtendo telefones para o Skype for Business Online](getting-phones-for-skype-for-business-online.md)


