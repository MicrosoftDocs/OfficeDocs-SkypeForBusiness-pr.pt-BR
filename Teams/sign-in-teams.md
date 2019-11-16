---
title: Entrar no Microsoft Teams usando a autenticação moderna
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/15/2018
audience: Admin
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Como entrar no Microsoft Teams usando a autenticação moderna.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a5698058cbfecd62f92cfe9f198657f7c280deff
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2019
ms.locfileid: "37563118"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a>Entrar no Microsoft Teams usando a autenticação moderna
==========================

O Microsoft Teams usa autenticação moderna para manter a experiência de entrada simples e segura. Para ver como os usuários entram no Microsoft Teams, leia entrar no Microsoft [Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).

## <a name="how-modern-authentication-works"></a>Como funciona a autenticação moderna

A autenticação moderna é um processo que permite que as equipes saibam que os usuários já inseriram suas credenciais (como o email e a senha de trabalho) em outro lugar, e não devem ser necessárias para inseri-las novamente para iniciar o aplicativo. A experiência irá variar dependendo de alguns fatores, como se os usuários estiverem trabalhando no Windows ou em um Mac. Isso também varia de acordo com a existência da autenticação de fator único ou da autenticação multifator da sua organização (autenticação multifator geralmente envolve a verificação de credenciais por meio de um telefone, o fornecimento de um código exclusivo, a inserção de um pino ou Apresentando uma impressão digital). Aqui está um resumo de cada cenário de autenticação moderna.

### <a name="windows-users"></a>Usuários do Windows: 

- Se os usuários já entrarem em outros aplicativos do Office por meio da sua conta empresarial do Office 365, quando eles iniciarem as equipes, eles serão colocados diretamente no aplicativo. Não é necessário inserir suas credenciais.

- Se os usuários não estiverem conectados à sua conta empresarial do Office 365 em qualquer outro lugar, quando iniciarem o Teams, eles serão solicitados a fornecer autenticação de fator único ou multifator (SFA ou MFA), dependendo do que a sua organização decidiu que gostaria da processo para implicar.

- Se os usuários estiverem conectados a um computador associado a um domínio, quando iniciarem o Teams, eles poderão ser solicitados a passar por mais uma etapa de autenticação, dependendo se a sua organização optou por exigir MFA ou se o computador já precisa de uma solicitação de conexão. Se o computador já precisa de uma MFA para entrar, quando ele abre equipes, o aplicativo é iniciado automaticamente.

### <a name="mac-users"></a>Usuários do Mac 

Quando os usuários iniciarem o Microsoft Teams, o computador não poderá receber credenciais da conta empresarial do Office 365 ou de qualquer um dos outros aplicativos do Office. Em vez disso, eles verão um prompt solicitando o SFA ou o MFA (dependendo das configurações da sua organização). Uma vez que os usuários inserem suas credenciais, não será preciso fornecê-las novamente. Desse ponto em diante, o Teams é iniciado automaticamente sempre que estiverem trabalhando no mesmo computador.

## <a name="switching-accounts-after-completing-modern-authentication"></a>Alternar entre contas após concluir a autenticação moderna

Se os usuários estiverem trabalhando em um computador associado a um domínio (por exemplo, se o locatário tiver habilitado o Kerberos), eles não poderão alternar entre contas de usuário depois que concluírem a autenticação moderna. Se os usuários não estiverem trabalhando em um computador associado a um domínio, eles poderão mudar de conta.

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a>Saindo do Microsoft Teams depois de concluir a autenticação moderna
Para sair do Teams, os usuários podem clicar na imagem do perfil na parte superior do aplicativo e, em seguida **, selecione sair**. Eles também podem clicar com o botão direito do mouse no ícone do aplicativo na barra de tarefas e, em seguida, selecionar **logout**. Depois de desconectarem-se do Teams, será necessário inserir suas credenciais novamente para iniciar o aplicativo.

## <a name="troubleshooting-modern-authentication"></a>Solução de problemas de autenticação moderna

A autenticação moderna está disponível para cada organização que usa o Teams, portanto, se os usuários não conseguem completar o processo, pode haver algo errado com o seu domínio ou com a conta corporativa do Office 365 da sua organização. 

Para obter mais informações, consulte [por que estou tendo problemas para entrar no Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).

