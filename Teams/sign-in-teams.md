---
title: Entrar no Teams usando a autenticação moderna
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: anwara
description: Saiba como funciona a autenticação moderna, como alternar entre contas e como solucionar problemas de autenticação moderna. Inclui como instruir o Teams a ignorar o preenchimento prévio do nome de usuário (UPN) ao entrar.
ms.custom: seo-marvel-apr2020
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: b8db647d5021aee124dec794e8711662de9f0a1c
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121361"
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

## <a name="teams-for-ios-and-android-users"></a>Teams para usuários do iOS e do Android

Ao entrar, os usuários móveis verão uma lista de todas as contas do Microsoft 365 que já estiveram ou estão atualmente conectadas em seus dispositivos. Os usuários podem tocar em qualquer uma das contas para entrar. Há dois cenários para se conectar no celular:
    
1. Se a conta selecionada estiver atualmente conectada a outros aplicativos do Office 365 ou do Microsoft 365, o usuário será direcionado diretamente para o Teams. Não é necessário que os usuários insiram suas credenciais.
    
2. Se o usuário não estiver conectado à sua conta do Microsoft 365 em nenhum outro lugar, será solicitado que insira autenticação de fator único ou multifator (SFA ou MFA), dependendo de qual sua organização configurou para as políticas de entrada de dispositivos móveis.

> [!NOTE]
> Para que os usuários possam viver a experiência de logon conforme ao descrito nesta seção, os dispositivos devem executar o Teams para iOS versão 2.0.13 (Build 2020061704) ou posterior, ou o Teams para Android versão 1416/1.0.0.2020061702 ou posterior.


### <a name="adding-multiple-accounts-to-teams"></a>Adicionar várias contas ao Teams.

O Teams para iOS e Android oferece suporte à adição de várias contas de um único dispositivo ao Teams. As imagens a seguir mostram como os usuários podem adicionar várias contas nas equipes.
    
:::image type="content" source="media/sign-in-multiple-accounts.png" alt-text="Adicionar várias contas ao Teams":::

### <a name="use-enterprise-mobility-management-to-control-which-accounts-can-sign-in-to-teams"></a>Usar o gerenciamento de mobilidade corporativa para controlar quais contas podem entrar no Teams

O Teams para iOS e Android oferece aos administradores de TI a capacidade de enviar configurações de conta para contas do Microsoft 365. Esse recurso funciona com qualquer provedor de MDM (Gerenciamento de Dispositivo Móvel) que use o canal de  [Configuração de Aplicativo Gerenciado](https://developer.apple.com/library/archive/samplecode/sc2279/Introduction/Intro.html)  para iOS ou o canal  [Android Enterprise](https://developer.android.com/work/managed-configurations)  para Android.

Para usuários registrados no Microsoft Intune, é possível implantar as configurações de conta usando o Intune no Portal do Azure.

Uma vez que a configuração da conta for feita no provedor de MDM, e após o usuário registrar o dispositivo, na página de logon, o Teams para iOS e Android mostrará apenas as contas permitidas na página de logon do Teams. O usuário pode tocar em qualquer uma das contas permitidas nesta página para entrar.

Defina os seguintes parâmetros de configuração no portal do Azure Intune para dispositivos gerenciados.


|Plataforma |Chave  |Valor  |
|---------|---------|---------|
|iOS     |  **IntuneMAMAllowedAccountsOnly**       | **Habilitado**: a única conta permitida é a conta de usuário gerenciada definida pela chave IntuneMAMUPN.<br> **Desabilitado** (ou qualquer valor que não seja uma correspondência que não diferencia maiúsculas e minúsculas para **Habilitado**): qualquer conta é permitida.        |
|iOS     |   **IntuneMAMUPN**      |   UPN da conta que pode entrar no Teams.<br> Para dispositivos registrados do Intune, o token {{userprincipalname}} pode ser usado para representar a conta de usuário registrada.       |
|Android     |**com.microsoft.intune.mam.AllowedAccountUPNs**         |    Somente as contas permitidas são as contas de usuário gerenciadas definidas por essa chave.<br> UPNs delimitadas por um ou mais pontos e vírgulas [;].<br> Para dispositivos registrados do Intune, o token {{userprincipalname}} pode ser usado para representar a conta de usuário registrada.

Depois que a configuração da instalação da conta for definida, o Teams restringirá a capacidade de entrar, para que somente as contas permitidas nos dispositivos registrados tenham acesso concedido.

Para criar uma política de configuração de aplicativo para dispositivos iOS/iPadOS gerenciados, confira  [Adicionar políticas de configuração de aplicativo para dispositivos iOS/iPadOS gerenciados](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-ios).

Para criar uma política de configuração de aplicativo para dispositivos Android gerenciados, confira  [Adicionar políticas de configuração de aplicativo para dispositivos Android gerenciados](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-android).


## <a name="switching-accounts-after-completing-modern-authentication"></a>Alternar contas após concluir a autenticação moderna

Se os usuários estiverem trabalhando em um computador ingressado no domínio (por exemplo, se o locatário tiver ativado o Kerberos), eles não poderão trocar de conta de usuário depois de concluir a autenticação moderna. Se os usuários não estiverem trabalhando em um computador ingressado no domínio, eles poderão alternar contas.

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a>Sair do Teams após concluir a autenticação moderna

Para sair do Teams, os usuários podem clicar na imagem do perfil na parte superior do aplicativo e, em seguida, selecionar **Sair**. Eles também podem clicar com o botão direito do mouse no ícone do aplicativo na barra de tarefas e, em seguida, selecionar **Fazer logoff**. Depois de sair do Teams, eles precisam inserir suas credenciais novamente para iniciar o aplicativo.

### <a name="signing-out-of-teams-for-ios-and-android"></a>Sair do Teams para iOS e Android

Os usuários de dispositivos móveis podem sair do Teams acessando o menu, escolhendo o menu **Mais** e, em seguida, **Sair**. Uma vez desconectado, os usuários precisarão inserir novamente suas credenciais na próxima vez em que iniciarem o aplicativo.

> [!NOTE]
> O Teams para Android usa SSO (logon único) para simplificar a experiência de entrada. Os usuários devem se desconectar de **todos** os aplicativos da Microsoft, além do Teams, para fazer logoff completamente na plataforma Android.

## <a name="urls-and-ip-address-ranges"></a>URLs e intervalos de endereços IP

O Teams exige conectividade com a Internet. Para entender os pontos de extremidade que devem ser acessados pelos clientes que usam o Teams nos planos do Office 365, no Governo e em outras nuvens, leia [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).

> [!IMPORTANT]
> O Teams atualmente exige o acesso (porta TCP 443) para o serviço Google ssl.gstatic.com (<https://ssl.gstatic.com)> para todos os usuários; tal exigência é obrigatória mesmo que você não esteja usando o Gstatic. O Teams removerá esse requisito em breve (início de 2020), e atualizaremos este artigo de forma adequada neste momento.

## <a name="troubleshooting-modern-authentication"></a>Solução de problemas de autenticação moderna

A autenticação moderna está disponível para todas as organizações que usam o Teams; portanto, se os usuários não puderem concluir o processo, pode haver algo errado com o seu domínio ou com sua conta corporativa ou de estudante da Microsoft.

Para saber mais, confira [Por que estou com problemas para entrar no Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)


## <a name="related-topics"></a>Tópicos relacionados

[Solução de problemas do Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)