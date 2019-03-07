---
title: Entrar no Microsoft Teams usando a autenticação moderna
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/15/2018
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Como entrar no Microsoft Teams usando autenticação moderna.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eec164da4dafe9be54272a72680cfa920d32d60c
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30458808"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a>Entrar no Microsoft Teams usando a autenticação moderna
==========================

Teams da Microsoft usa autenticação moderna para manter a experiência de entrada, simples e segura. Para ver como os usuários fazem logon equipes, leia a [entrar em equipes](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).

## <a name="how-modern-authentication-works"></a>Moderno como funciona a autenticação

Autenticação moderna é um processo que permite que as equipes saber que os usuários já foram inseridos suas credenciais (como seu trabalho email e senha) em outro lugar e eles não devem ser necessário inseri-las novamente para iniciar o aplicativo. A experiência variará dependendo de dois fatores, como se os usuários estão trabalhando no Windows ou em um Mac. Ele também irá variar dependendo se a sua organização tiver habilitado a autenticação de fator único ou a autenticação multifator (geralmente, a autenticação multifator envolve verificando credenciais por meio de um telefone, fornecendo um código exclusivo, inserindo um PIN, ou Apresentando uma impressão digital). Aqui está um resumo de cada cenário de autenticação moderno.

### <a name="windows-users"></a>Usuários do Windows: 

- Se os usuários já tenham entrado em para outros aplicativos do Office por meio de sua conta do Office 365 Enterprise, quando eles começarem a equipes serão levados retas para o aplicativo. Não é necessário para que eles possam Insira suas credenciais.

- Se os usuários não estiver conectados à sua conta do Office 365 Enterprise em outros lugares, quando eles começarem a equipes, ele são solicitados a fornecer autenticação fator único ou vários fator (SFA ou MFA), dependendo de qual sua organização tiver decidido gostariam de processo envolve.

- Se os usuários estiver conectados a um computador associado ao domínio, quando eles começarem a equipes, eles podem ser solicitados atravessar uma etapa de autenticação mais, dependendo se a sua organização tiver optado para exigir MFA ou se o seu computador já exige MFA entrar. Se seu computador já exigir MFA entrar, quando eles abrem backup equipes, o aplicativo automaticamente inicia.

### <a name="mac-users"></a>Usuários do Mac 

Quando os usuários iniciam equipes, seu computador não poderá receber suas credenciais de sua conta do Office 365 Enterprise ou para qualquer um dos seus outros aplicativos do Office. Em vez disso, eles verão um aviso perguntando-los para SFA ou MFA (dependendo das configurações da sua organização). Depois que os usuários inserirem suas credenciais, eles não seja necessário para fornecer-lhes novamente. A partir desse momento, as equipes automaticamente inicia sempre eles estiver trabalhando no mesmo computador.

## <a name="switching-accounts-after-completing-modern-authentication"></a>Alternando contas depois de concluir a autenticação moderna

Se os usuários estão trabalhando em um computador associado ao domínio (por exemplo, se seu locatário tiver habilitado o Kerberos), eles não podem alternar contas de usuário quando concluírem autenticação moderna. Se os usuários não estiver trabalhando em um computador associado ao domínio, eles podem alternar contas.

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a>Saindo do Microsoft Teams depois de concluir a autenticação moderna

Para sair de equipes, os usuários podem clique em sua foto de perfil, na parte superior do aplicativo e selecione **Sair**. Eles podem também com o botão direito no ícone do aplicativo na sua barra de tarefas e selecione **efetuar logout**. Depois que eles já saírem equipes, elas precisam inserir suas credenciais novamente para iniciar o aplicativo.

## <a name="troubleshooting-modern-authentication"></a>Solução de problemas de autenticação moderna

Autenticação moderna está disponível para todas as organizações que usa as equipes, portanto se os usuários não conseguem concluir o processo, pode haver algo errada com seu domínio ou a conta do Office 365 Enterprise da sua organização. 

Para obter mais informações, consulte [por que estou tendo problemas para entrar na Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).

