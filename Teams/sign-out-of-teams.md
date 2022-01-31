---
title: Sair do Microsoft Teams
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: sbhatta
description: Saiba como sair do Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.localizationpriority: high
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: ba5789dac9d54de153c6d4c712a2d68367ad79c0
ms.sourcegitcommit: 8d728ca42dc917a28b94e2de84ce4f5b2515d485
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2021
ms.locfileid: "61513592"
---
# <a name="sign-out-of-microsoft-teams"></a>Sair do Microsoft Teams

Recomendamos que os usuários permaneçam conectados ao aplicativo Microsoft Teams para continuar recebendo chats, chamadas de entrada e outras atividades. Entendemos que, às vezes, os usuários podem querer sair do aplicativo Teams por vários motivos:

- Porque eles terminaram de usar o Teams pelo dia
- Eles querem usar uma conta diferente
- Porque eles estão em um dispositivo que compartilham com outra pessoa

Por esses e outros motivos, o Teams permite que você saia do aplicativo e encerre sua sessão.

## <a name="account-sharing-between-apps"></a>Compartilhamento de conta entre aplicativos

Sistemas operacionais modernos permitem o compartilhamento de contas entre diferentes aplicativos em um dispositivo. Esse design de logon único (SSO) permite que os usuários usem vários aplicativos em seus dispositivos sem exigir que eles se conectem a todos os aplicativos. O Teams não controla esse comportamento, mas aproveita a conveniência que esse design oferece para a experiência do usuário final.

O SSO tem um impacto importante na saída. Quando os usuários sai do Teams, os dados associados à sua conta são removidos do aplicativo Teams, mas outros aplicativos no dispositivo podem continuar a ter acesso à sua conta. Isso também significa que talvez os usuários não sejam solicitados a reinserir suas credenciais se optarem por entrar novamente no Teams com a mesma conta.

## <a name="sign-out-of-teams-on-desktop"></a>Sair do Teams no computador

Para sair do cliente da área de trabalho do Teams ou do navegador, selecione sua imagem de perfil na parte superior do aplicativo e selecione **Sair**.

Para o aplicativo da área de trabalho, você também pode clicar com o botão direito do mouse no ícone do aplicativo na barra de tarefas e, em seguida, selecionar **Sair**.

Se você tiver várias contas adicionadas, precisará sair de cada conta individual. Depois de sair das contas no Teams, talvez seja necessário inserir suas credenciais novamente na próxima inicialização do aplicativo para acessar sua conta.

## <a name="sign-out-of-teams-on-mobile-devices"></a>Sair do Teams em dispositivos móveis

No celular, você pode sair do Teams acessando o menu, selecionando o menu **Mais** e, em seguida, selecionando **Sair**. Depois de sair, você precisará reinserir suas credenciais na próxima vez que iniciar o aplicativo.

### <a name="global-sign-in-and-sign-out-for-frontline-workers"></a>Entrada e saída globais para funcionários do Frontline

O aplicativo do Microsoft Teams para Android agora oferece suporte para entrada e saída global, para fornecer uma experiência de entrada e saída sem complicações para funcionários da linha de frente. Os funcionários podem escolher um dispositivo do grupo de dispositivos compartilhados e fazer uma única entrada para "torná-la deles" durante todo o período do turno. No final do turno, eles devem ser capazes de executar a saída para sair globalmente no dispositivo. Isto removerá do dispositivo todas as informações pessoais e da empresa para que eles possam devolver o dispositivo ao grupo de dispositivos. Para obter esse recurso, o dispositivo deve estar no modo compartilhado. Para saber como configurar um dispositivo compartilhado, consulte [Como usar um modo de dispositivo compartilhado no Android](/azure/active-directory/develop/tutorial-v2-shared-device-mode#set-up-an-android-device-in-shared-mode).

## <a name="manual-cleanup"></a>Limpeza Manual

Embora seja raro, é possível que o Teams não consiga limpar tudo após a saída. Com base em relatórios de usuário, as causas comuns incluem arquivos bloqueados por um serviço em execução no sistema, mas pode haver outros motivos que dependem das configurações de dispositivo ou políticas de um indivíduo e permissões de usuário aplicadas ao dispositivo.

Uma manifestação comum desse problema é que o Teams tentará selecionar automaticamente uma conta existente para conectar o usuário. Em situações como essa, o usuário pode querer limpar manualmente o cache local do Teams. Saiba mais em [Entrar ou remover uma conta do Teams](https://support.microsoft.com/office/sign-out-or-remove-an-account-from-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487?ui=en-US&rs=en-US&ad=US).

## <a name="related-topics"></a>Tópicos relacionados

[Entrar ou remover uma conta do Teams](https://support.microsoft.com/office/sign-out-or-remove-an-account-from-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487?ui=en-US&rs=en-US&ad=US)