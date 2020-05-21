---
title: Entrar no Teams usando a autenticação moderna
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Saiba como funciona a autenticação moderna, como alternar entre contas e como solucionar problemas de autenticação moderna. Inclui como instruir o Teams a ignorar o preenchimento prévio do nome de usuário (UPN) ao entrar.
ms.custom: seo-marvel-apr2020
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 63bfd0cb9fe4292b180dfc6a0c7852b3c90a8bc4
ms.sourcegitcommit: 624bd511b96cf213483d3ea8f27b20a91d955550
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2020
ms.locfileid: "44330536"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a>Entrar no Microsoft Teams usando a autenticação moderna
==========================

A Microsoft recomenda que as organizações usem versões recentes do Windows 10 com a configuração de Ingresso do Domínio Híbrido ou Ingresso no Azure AD. Isso garante que as contas dos usuários sejam configuradas no Gerenciador de Contas da Web do Windows, que habilita o logon único para o Teams e outros aplicativos da Microsoft. Isso oferece uma melhor experiência de usuário (entrada silenciosa) e uma melhor postura de segurança.

O Microsoft Teams usa autenticação moderna para manter a experiência de inscrição simples e segura. Para ver como os usuários entram no Teams, leia [Entrar no Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).

## <a name="how-modern-authentication-works"></a>Como funciona a autenticação moderna

A autenticação moderna é um processo que permite que o Teams saiba que os usuários já inseriram suas credenciais (como e-mail e senha de trabalho) em outro local e não devem ser obrigados a digitá-las novamente para iniciar o aplicativo. A experiência variará dependendo de alguns fatores, como se os usuários estiverem trabalhando no Windows ou em um Mac. Também variará dependendo de sua organização ter ativado a autenticação de fator único ou a autenticação de multifator (a autenticação multifator geralmente envolve a verificação de credenciais por telefone, fornecendo um código exclusivo, a inserção de um PIN ou a impressão digital). Este é um resumo de cada cenário de autenticação moderna.

### <a name="windows-users"></a>Usuários do Windows

- Se os usuários já tiverem entrado no Windows ou em outros aplicativos do Office com a conta corporativa ou de estudante, quando iniciarem o Teams, serão direcionados diretamente para o aplicativo. Não é necessário que eles insiram suas credenciais.

- A Microsoft recomenda usar a versão 1903 ou posterior do Windows 10 para obter a melhor experiência de logon único.

- Se os usuários não estiverem conectados à sua conta corporativa ou de estudante da Microsoft em nenhum outro lugar, ao iniciarem o Teams, será solicitado que forneçam autenticação de fator único ou multifator (SFA ou MFA), dependendo do que sua organização decidiu que eles gostariam que o processo envolvesse.

- Se os usuários estiverem conectados a um computador ingressado no domínio, quando iniciarem o Teams, poderão ser solicitados a executar mais uma etapa de autenticação, dependendo se sua organização optou por exigir MFA ou se o computador já exige que o MFA faça logon. Se o computador deles já exigir MFA para entrar, quando eles abrirem o Teams, o aplicativo será iniciado automaticamente.

- Em computadores que ingressaram em domínios, quando o SSO não for possível, o Teams poderá preencher a sua tela de logon com o nome principal do usuário (UPN). Há casos em que você não quer que isso aconteça, principalmente se a sua organização usa UPNs diferentes no local e no Azure Active Directory. Se esse for o caso, você poderá usar a seguinte chave do registro do Windows para desativar o pré-registro com UPN:

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

    > [!NOTE]
    > Pular ou ignorar o pré-preenchimento do nome do usuário para nomes de usuários que terminam com ".local" ou ".corp" está ativado por padrão, por isso, não é necessário definir uma chave de registro para desativá-los.


### <a name="mac-users"></a>Usuários do Mac

No MacOS, O Teams solicitará que os usuários insiram o nome de usuário e as credenciais e poderá solicitar a autenticação multifatorial, dependendo das configurações da sua organização. Quando os usuários inserem suas credenciais, eles não precisarão fornecê-las novamente. A partir desse ponto em diante, o Teams será iniciado automaticamente sempre que estiverem trabalhando no mesmo computador.

## <a name="switching-accounts-after-completing-modern-authentication"></a>Alternar contas após concluir a autenticação moderna

Se os usuários estiverem trabalhando em um computador ingressado no domínio (por exemplo, se o locatário tiver ativado o Kerberos), eles não poderão trocar de conta de usuário depois de concluir a autenticação moderna. Se os usuários não estiverem trabalhando em um computador ingressado no domínio, eles poderão alternar contas.

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a>Sair do Teams após concluir a autenticação moderna

Para sair do Teams, os usuários podem clicar na imagem do perfil na parte superior do aplicativo e, em seguida, selecionar **Sair**. Eles também podem clicar com o botão direito do mouse no ícone do aplicativo na barra de tarefas e, em seguida, selecionar **Fazer logoff**. Depois de sair do Teams, eles precisam inserir suas credenciais novamente para iniciar o aplicativo.

## <a name="urls-and-ip-address-ranges"></a>URLs e intervalos de endereços IP

O Teams exige conectividade com a Internet. Para entender os pontos de extremidade que devem ser acessados pelos clientes que usam o Teams nos planos do Office 365, no Governo e em outras nuvens, leia [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).

> [!IMPORTANT]
> O Teams atualmente exige o acesso (porta TCP 443) para o serviço Google ssl.gstatic.com (<https://ssl.gstatic.com)> para todos os usuários; tal exigência é obrigatória mesmo que você não esteja usando o Gstatic. O Teams removerá esse requisito em breve (início de 2020), e atualizaremos este artigo de forma adequada neste momento.

## <a name="troubleshooting-modern-authentication"></a>Solução de problemas de autenticação moderna

A autenticação moderna está disponível para todas as organizações que usam o Teams; portanto, se os usuários não puderem concluir o processo, pode haver algo errado com o seu domínio ou com sua conta corporativa ou de estudante da Microsoft.

Para saber mais, confira [Por que estou com problemas para entrar no Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)
