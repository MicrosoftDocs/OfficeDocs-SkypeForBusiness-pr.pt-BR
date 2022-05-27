---
title: Entrar no Microsoft Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: anwara
description: Saiba como funciona a autenticação moderna, como alternar entre contas e como solucionar problemas de autenticação moderna. Inclui como dizer às equipes para ignorar o pré-preenchimento do nome do usuário (UPN) ao fazer a entrada.
ms.custom: seo-marvel-apr2020
ms.localizationpriority: high
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: b6fb93bf7f8e3278ba4fba16604769c6f8f10e36
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681602"
---
# <a name="sign-in-to-microsoft-teams"></a>Entrar no Microsoft Teams

## <a name="windows-users"></a>Usuários do Windows

A Microsoft recomenda que as organizações usem versões recentes do Windows 10 com a configuração de Ingresso do Domínio Híbrido ou Ingresso no Azure AD. O uso de versões recentes garante que as contas dos usuários sejam preparadas no Gerenciador de Contas da Web do Windows, que por sua vez permite o logon único no Teams e em outros aplicativos da Microsoft. A entrada única fornece uma melhor experiência do usuário (logon silencioso) e uma melhor postura de segurança.

O Microsoft Teams usa autenticação moderna para manter a experiência de inscrição simples e segura. Para ver como os usuários entram no Teams, leia [Entrar no Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).

### <a name="how-modern-authentication-works"></a>Como funciona a autenticação moderna

A autenticação moderna é um processo que permite que as Equipes saibam que os usuários já inseriram suas credenciais, como email de trabalho e senha em outro lugar, e não há necessidade de inseri-las novamente para iniciar o aplicativo. A experiência varia dependendo de alguns fatores, como, por exemplo, se os usuários estão trabalhando no Windows ou em um Mac. Ele também variará dependendo se sua organização habilitou a autenticação de fator único ou a autenticação multifator. A autenticação multifator geralmente envolve a verificação de credenciais por meio de um telefone, fornecendo um código exclusivo, inserindo um PIN ou apresentando uma impressão digital. Este é um resumo de cada cenário de autenticação moderna.

A autenticação moderna está disponível para todas as organizações que usam Microsoft Teams. Se os usuários não conseguirem concluir o processo, pode haver um problema subjacente com a configuração do Azure Active Directory da sua organização. Para obter mais informações, confira [Por que estou tendo problemas para entrar no Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)

- Se os usuários já assinaram o Windows ou outros aplicativos do Office com sua conta de trabalho ou de escola, quando iniciam o Teams são levados diretamente para o aplicativo. Não há necessidade de que eles entrem com suas credenciais.

- A Microsoft recomenda usar do Windows 10 versão 1903 ou posterior para a melhor experiência de Single Sign-On.

- Se os usuários não estiverem conectados à conta corporativa ou de estudante da Microsoft em outro lugar, quando iniciarem o Teams, eles serão solicitados a fornecer autenticação de fator único ou multifator (SFA ou MFA). Esse processo depende do que sua organização decidiu que gostaria que o procedimento de entrada exigia.

- Se os usuários estiverem conectados a um computador com domínio, quando se inicia o Teams, eles poderão ser solicitados a passar por mais uma etapa de autenticação, dependendo se sua organização optou por requerer o MFA ou se seu computador já requer o MFA para se conectar. Se o computador deles já exige que o MFA faça o login, quando abrir o Teams, o aplicativo é iniciado automaticamente.

- Em computadores que ingressaram em domínios, quando o SSO não for possível, o Teams poderá preencher a sua tela de logon com o nome principal do usuário (UPN). Há casos em que você não quer que isso aconteça, principalmente se a sua organização usa UPNs diferentes no local e no Azure Active Directory. Se esse for o caso, você poderá usar a seguinte chave do registro do Windows para desativar o pré-registro com UPN:

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

    > [!NOTE]
    > Pular ou ignorar o pré-preenchimento do nome do usuário para nomes de usuários que terminam com ".local" ou ".corp" está ativado por padrão, por isso, não é necessário definir uma chave de registro para desativá-los.

### <a name="signing-in-to-another-account-on-a-domain-joined-computer"></a>Login em outra conta em um computador Associado ao Domínio

Os usuários em um computador Associado a um Domínio podem não conseguir entrar no Microsoft Teams com outra conta no mesmo domínio do Active Directory.

## <a name="macos-users"></a>Usuários do macOS

No macOS, o Teams solicitará que os usuários digitem seu nome de usuário e credenciais, e podem solicitar uma autenticação multifator, dependendo das configurações da sua organização. Quando os usuários inserem suas credenciais, eles não precisarão fornecê-las novamente. A partir desse ponto em diante, o Teams será iniciado automaticamente sempre que estiverem trabalhando no mesmo computador.

## <a name="teams-on-ios-and-android-users"></a>Microsoft Teams nos usuários iOS e Android

Ao entrar, os usuários de dispositivos móveis verão uma lista de todas as contas do Microsoft 365 que estão atualmente conectadas ou que já haviam feito login em seus dispositivos. Os usuários podem utilizar qualquer uma das contas para entrar. Há dois cenários para se conectar no celular:

1. Se a conta selecionada estiver atualmente registrada em outros aplicativos Office 365 ou Microsoft 365, então o usuário será levado diretamente ao Teams. Não há necessidade de o usuário digitar suas credenciais.

2. Se o usuário não estiver conectado à sua conta do Microsoft 365 em nenhum outro lugar, será solicitado que ele forneça uma autenticação de fator único ou multifator (SFA ou MFA), dependendo do que a organização configurou para as políticas de entrada em dispositivos móveis.

> [!NOTE]
> Para que os usuários possam viver a experiência de logon conforme ao descrito nesta seção, os dispositivos devem executar o Teams para iOS versão 2.0.13 (Build 2020061704) ou posterior, ou o Teams para Android versão 1416/1.0.0.2020061702 ou posterior.

## <a name="using-teams-with-multiple-accounts"></a>Usando o Microsoft Teams com várias contas

O Microsoft Teams para iOS e Android suporta o uso de várias contas corporativas ou estudantes e várias contas pessoais lado a lado. Os aplicativos de área de trabalho do Microsoft Teams oferecerão suporte a uma conta trabalho/escola e uma conta pessoal lado a lado em dezembro de 2020, com suporte para várias contas corporativa/estudante em uma data posterior.

As imagens a seguir mostram como os usuários podem adicionar várias contas nos aplicativos móveis do Microsoft Teams.

:::image type="content" source="media/sign-in-multiple-accounts.png" alt-text="Adicionar várias contas ao Microsoft Teams.":::

## <a name="restrict-sign-in-to-teams"></a>Restringir login para o Microsoft Teams

A organização pode querer restringir como os aplicativos aprovados pela empresa são usados ​​em dispositivos gerenciados, por exemplo, para restringir a capacidade dos alunos ou funcionários de acessar dados de outras organizações ou usar aplicativos aprovados pela empresa para cenários pessoais. Essas restrições podem ser aplicadas pela configuração de Políticas de Dispositivos que os aplicativos o Microsoft Teams reconhece.

### <a name="how-to-restrict-sign-in-on-mobile-devices"></a>Como restringir o login em dispositivos móveis

O Microsoft Teams para iOS e Android oferecem aos administradores de TI a capacidade de enviar configurações de conta para contas do Microsoft 365. Esse recurso funciona com qualquer provedor de Gerenciamento de Dispositivo móvel (MDM) que usa o canal [Configuração de Aplicativo Gerenciado](https://developer.apple.com/library/archive/samplecode/sc2279/Introduction/Intro.html) para iOS ou o canal [ Android Empresarial](https://developer.android.com/work/managed-configurations) para Android.

Para usuários inscritos no Microsoft Intune, você pode implantar as definições de configuração da conta usando o Intune no portal do Azure.

Depois que a configuração de configuração da conta for configurada no provedor de MDM e depois que o usuário registrar seu dispositivo, na página de entrada, o Teams para iOS e Android mostrará apenas as contas permitidas na página de entrada do Teams. O usuário pode tocar em qualquer uma das contas permitidas nesta página para fazer login.

Defina os seguintes parâmetros de configuração no portal do Azure Intune para dispositivos gerenciados.

|Plataforma |Chave  |Valor  |
|---------|---------|---------|
|iOS     |  **IntuneMAMAllowedAccountsOnly**       | **Habilitado**: a única conta permitida é a conta de usuário gerenciada definida pela chave IntuneMAMUPN.<br> **Desabilitado** (ou qualquer valor que não seja uma correspondência que não diferencia maiúsculas e minúsculas para **Habilitado**): qualquer conta é permitida.        |
|iOS     |   **IntuneMAMUPN**      |   UPN da conta que pode entrar no Teams.<br> Para dispositivos registrados do Intune, o token {{userprincipalname}} pode ser usado para representar a conta de usuário registrada.       |
|Android     |**com.microsoft.intune.mam.AllowedAccountUPNs**         |    Somente as contas permitidas são as contas de usuário gerenciadas definidas por essa chave.<br> Um ou mais pontos e vírgulas;] - UPNs delimitados.<br> Para dispositivos registrados do Intune, o token {{userprincipalname}} pode ser usado para representar a conta de usuário registrada.

Depois que a configuração da instalação da conta for definida, o Teams restringirá a capacidade de entrar, para que somente as contas permitidas nos dispositivos registrados tenham acesso concedido.

Para criar uma política de configuração de aplicativo para dispositivos iOS/iPadOS gerenciados, confira [Adicionar políticas de configuração de aplicativo para dispositivos iOS/iPadOS gerenciados](/mem/intune/apps/app-configuration-policies-use-ios).

Para criar uma política de configuração de aplicativo para dispositivos Android gerenciados, confira [Adicionar políticas de configuração de aplicativo para dispositivos Android gerenciados](/mem/intune/apps/app-configuration-policies-use-android).

### <a name="how-to-restrict-sign-in-on-desktop-devices"></a>Como restringir o login em dispositivos desktop

Os aplicativos do Teams no Windows e no macOS estão ganhando suporte para políticas de dispositivo que restringem o acesso à sua organização. As políticas podem ser definidas por meio de soluções usuais de Gerenciamento de Dispositivos, como MDM (Gerenciamento de dispositivos Móveis) ou GPO (Objeto de Política de Grupo). 

Quando esta política é configurada em um dispositivo, os usuários só podem entrar com contas hospedadas em um locatário do Azure Active Directory incluído na "Lista de Permissões de Locatário" definida na política. A política se aplica a todos os logins, incluindo contas iniciais e adicionais. Se sua organização abrange vários locatários do Azure Active Directory, você pode incluir várias IDs de Locatário na Lista de Permissões. Os links para adicionar outra conta podem continuar visíveis no aplicativo Microsoft Teams, mas não estarão operacionais.

> [!NOTE]
> 
>1. A política restringe apenas as assinaturas. Ela não restringe a possibilidade de os usuários serem convidados como convidados em outros locatários do Microsoft Azure Active Directory, ou mudar para esses outros locatários (onde os usuários foram convidados como convidados).
>2. A política requer o Teams para Windows versão 1.3.00.30866 ou superior e o Teams para macOS versão 1.3.00.30882 (lançado em meados de novembro de 2020).

**Políticas para Windows** Os arquivos de Modelo Administrativo (ADMX/ADML) estão disponíveis no [Centro de Download](https://www.microsoft.com/download/details.aspx?id=49030) (o nome descritivo da configuração de política no arquivo de modelo administrativo é "Restringir a entrada no Teams para as contas nos locatários específicos"). Além disso, você pode definir chaves manualmente no Registro do Windows:

- Nome do valor: RestrictTeamsSignInToAccountsFromTenantList
- Tipo de Valor: Cadeia de Caracteres
- Dados do Valor: ID do Locatário ou lista separada por vírgulas de IDs do Locatário
- Caminho: use um dos seguintes

 Computer\HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Cloud\Office\16.0\Teams Computer\HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Teams Computer\HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\16.0\Teams

Exemplo: SOFTWARE\Policies\Microsoft\Office\16.0\Teams\RestrictTeamsSignInToAccountsFromTenantList = ID do Locatário ou SOFTWARE\Policies\Microsoft\Office\16.0\Teams\RestrictTeamsSignInToAccountsFromTenantList = ID do Locatário 1, ID do Locatário 2, ID do Locatário 3

**Políticas para macOS** Para dispositivos gerenciados macOS, use .plist para implantar restrições de login. O perfil de configuração é um arquivo .plist que consiste em entradas identificadas por uma chave (que denota o nome da preferência), seguida por um valor, que depende da natureza da preferência. Os valores podem ser simples (como um valor numérico) ou complexos, como uma lista aninhada de preferências.

- Domínio: com.microsoft.teams
- Chave: RestrictTeamsSignInToAccountsFromTenantList
- Tipo de Dados: Cadeia de Caracteres
- Comentários: insira uma lista separada por vírgulas de IDs de locatário do Azure Active Directory

### <a name="global-sign-in"></a>Entrada global

O aplicativo Teams Para Android agora é compatível com a entrada global, para fornecer uma experiência de entrada sem complicações para trabalhadores de linha de frente. Os funcionários podem escolher um dispositivo do grupo de dispositivos compartilhados e fazer uma única entrada para "torná-la deles" durante todo o período do turno. No final do turno, eles devem ser capazes de fazer o logoff para fazer o logoff globalmente no dispositivo. Consulte [Sair do Teams](sign-out-of-teams.md) para saber mais. Isto removerá do dispositivo todas as informações pessoais e da empresa para que eles possam devolver o dispositivo ao grupo de dispositivos. Para obter esse recurso, o dispositivo deve estar no modo compartilhado. Certifique-se de encerrar qualquer reunião ativa ou ligar no dispositivo antes de sair. Para saber como configurar um dispositivo compartilhado, consulte [Como usar um modo de dispositivo compartilhado no Android](/azure/active-directory/develop/tutorial-v2-shared-device-mode#set-up-an-android-device-in-shared-mode).

A experiência de entrada é semelhante à nossa experiência de entrada padrão do Teams.

## <a name="urls-and-ip-address-ranges"></a>URLs e intervalos de endereços IP

O Teams requer conectividade com a Internet. Para entender os pontos de extremidade que devem ser acessíveis aos clientes que usam o Teams nos planos do Office 365, Governo e outras nuvens, leia [URLs do Office 365 e intervalos de endereços de IP](/office365/enterprise/urls-and-ip-address-ranges).


## <a name="related-topics"></a>Tópicos relacionados

[Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams)
