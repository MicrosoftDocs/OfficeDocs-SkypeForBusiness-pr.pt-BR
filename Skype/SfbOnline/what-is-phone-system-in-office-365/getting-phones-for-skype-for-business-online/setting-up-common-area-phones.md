---
title: Configurar telefones de área comum
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: Aprenda as etapas de implantação para obter o firmware correto, atualizá-lo, se necessário, atribuir licenças e definir configurações para Telefones de Área Comum.
ms.openlocfilehash: cbf1c5f211eba09ee90a0358b175332fa64de4e2
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726970"
---
# <a name="set-up-common-area-phones"></a>Configurar telefones de área comum

[!INCLUDE [sfbo-retirement](../../../Hub/includes/sfbo-retirement.md)]
Um CAP (telefone de área comum) é normalmente colocado em áreas como saguões ou outras áreas disponíveis para muitas pessoas. Por exemplo, telefones de áreas de recepção, interfones ou telefones de salas de reunião, os CAPs são configurados como dispositivos em vez de usuários e se conectam automaticamente a uma rede. Nas etapas a seguir, ajudaremos você a configurar uma conta para o Sistema de Telefonia com planos de chamada, de modo que você possa implantar esses tipos de telefones na sua organização.

## <a name="prerequisites-for-common-area-phones"></a>Pré-requisitos para telefones de área comum

A primeira coisa a ser feita é confirmar que você já:

- Comprou a licença do Telefone de Área Comum e um Plano de Chamadas.
- Pesquisou e comprou telefones aprovados (veja a lista [aqui](deploying-skype-for-business-online-phones.md)).
- Atualizou o firmware em seus telefones (veja o firmware suportado [neste tópico](getting-phones-for-skype-for-business-online.md)).  Você pode verificar o firmware do seu telefone da seguinte forma:
  - **Telefones VVX polycom**: Vá **para** Configurações Aplicativo principal da plataforma  >    >    >  **de**  >  status.
  - **Telefones yealink**: Vá para **Status** na tela do telefone principal.
  - **AudioCodes telefones**: Vá para **Menu Versão** do Firmware de Status do Dispositivo na tela  >    >   inicial.
  - **Telefones do Lync Telefone Edition (LPE)**: Vá para **Menu**  >  **Informações do Sistema** da tela inicial.

    As atualizações de firmware são gerenciadas pelo Skype for Business Service. Todo firmware de telefone certificado pelo Skype for Business é carregado para o servidor de atualização do Skype for Business e a atualização do dispositivo é habilitada em todos os telefones por padrão.

    Dependendo do tempo de inatividade no telefone e dos intervalos de sondagem, os telefones baixarão e instalarão automaticamente as versões certificadas mais recentes. Você pode desabilitar as configurações de atualização do dispositivo usando o cmdlet  [Set-CsIPPhonePolicy](/powershell/module/skype/set-csipphonepolicy) e definindo o *parâmetro EnableDeviceUpdate* como `false` .

## <a name="setting-up-a-common-area-phone"></a>Configuração de um telefone de área comum
Você precisará seguir estas etapas:

### <a name="step-1---buy-the-licenses"></a>Etapa 1 - Compre as licenças
1. No centro de administração, vá para **Cobrança**  >  **Serviços de Compra** e adicione Outros **planos**.

    ![Captura de tela da licença Telefone Área Comum.](../../images/cap-license.png)
2. Clique em **Telefone de Área Comum** > **Comprar agora** > na página **Finalizar compra** clique em **Comprar agora**.
3. Clique em expandir **Assinaturas de complementos** e depois clique em comprar um Plano de Chamadas. Escolha o Plano **de Chamada Doméstica** ou o Plano de Chamada Doméstico e **Internacional.**

> [!Note]
> Você não precisa de uma licença do Sistema de Telefonia. Ela está incluída na licença do **Telefone da Área Comum**.

Para mais informações sobre licenças, veja [Licenciamento de complementos do Skype for Business e Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Etapa 2 - Criar uma nova conta de usuário para o telefone e atribuir as licenças
1. No centro de administração, vá para **Usuários**  >  **Ativos**  >  **Adicionar um usuário**.
2. Coloque um **Nome de usuário** como "Principal" para o primeiro nome e "Recepção" para o segundo nome.
3. Coloque um **Nome para exibição** se "Recepção Principal"não for gerado automaticamente.
4. Coloque um **Nome de usuário** como "RecepçãoPrincipal" ou "LobbyPrincipal".
5. Para telefones de área comum, você pode definir uma senha manualmente ou usar a mesma senha para todos os telefones. Além disso, você pode desmarcar **Fazer com que esse usuário mude a senha quando entrar pela primeira vez**.
6. Se você ainda estiver nessa página, atribua as licenças a esse usuário. Na mesma página, clique para expandir as **Licenças de produto**. Ative o seguinte:
   - Telefone de Área Comum
   - Você precisa escolher um **Plano de Chamadas Domésticas** ou um **Plano de Chamadas Domésticas e Internacionais**.

     A atribuição das licenças ficará assim:

     ![TurnOnCapLicense.png.](../../images/cap-license-turn-on.png)

     > [!Note]
     > Só para você saber, o Skype for Business Plan 2 está incluído na licença do **Telefone de Área Comum**.

Para mais detalhes, veja [Adicionar um usuário](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Etapa 3 - Atribuir um número de telefone à conta de usuário do Telefone de Área Comum

![Um ícone mostrando o logotipo Skype for Business.](../../images/sfb-logo-30x30.png) Atribuir um número de telefone ao usuário usando o **Skype for Business de administração**

1. No centro de administração > **centros de administração**  >  **Skype for Business**.
2. No **Centro de administração do Skype for Business** >  **Voz** > **Números de telefone**.
3. Selecione um número na lista de números de telefone e clique em **Atribuir**.
4. Na página **Atribuir**, na caixa **Usuário de voz** digite o nome do usuário usado para o telefone e, em seguida, selecione o usuário no menu suspenso **Selecionar um usuário de voz**.
5. Na página, você precisa adicionar um endereço de emergência. Depois de pesquisar, acesse **Selecionar endereço de emergência** para escolher o endereço certo para você.
6. Clique em **Salvar** e seu usuário ficará assim:

    ![Captura de tela do número de telefone do usuário.](../../images/cap-user-number.png)

   > [!Note]
   > Os usuários só aparecerão se tiverem uma licença do **Sistema de Telefonia** aplicada. Quando fizer isso, pode levar um tempo para que o usuário apareça na lista.

Para mais detalhes, veja [Obtenção de números de telefone para seus usuários](/microsoftteams/getting-phone-numbers-for-your-users).

Se você estiver se perguntando, você também pode pegar seu número de telefone que você tem com outra operadora e "*porta*" ou transferi-los para Microsoft 365 ou Office 365. Veja, [Transferir números de telefone para Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams).

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
    2. Selecione **Credenciais do usuário** e depois **Entrada na Web (CAP)** para gerar um código.
    3. Acesse o [portal de configuração](https://aka.ms/skypecap) e entre como **administrador**.
    4. Insira o nome de exibição (p. ex., Recepção Principal).

       > [!Note]
       > Se a caixa de seleção **Pesquisar apenas Telefones de Área Comum** estiver marcada, desmarque e pesquise novamente.

    5. Na janela de código de pareamento, insira o código exibido no telefone e clique em **Provisão**.

        Após essa última etapa, é possível entrar automaticamente.


> [!NOTE]
> O site de configuração do CAP informa que ele redefinirá a senha da conta CAP para uma senha aleatória. Observe que a conta à qual o CAP está se referindo é a conta do Active Directory do Azure (AAD). Se você criou a conta somente no AAD, então o processo é direto. Se você tiver sincronizado um Active Directory local com o AAD e usar um IDP ou ADFS de terceiros, o provisionamento cap falhará. Nesse caso, você precisa usar apenas uma conta Microsoft 365 ou Office 365/Azure Active Directory (por exemplo, uma conta com **onmicrosoft.com** domínio) para que o provisionamento cap funcione.


### <a name="related-topics"></a>Tópicos relacionados

- Saiba mais sobre os telefones disponíveis em [Implantação de telefones do Skype for Business Online](deploying-skype-for-business-online-phones.md).
- [Obtendo telefones do Skype for Business Online](getting-phones-for-skype-for-business-online.md)
