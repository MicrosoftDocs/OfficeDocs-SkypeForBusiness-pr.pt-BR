---
title: Criptografia de ponta a ponta para o Microsoft Teams
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 03/08/2022
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: ashgupt
description: Saiba mais sobre os recursos de criptografia aprimorados no Microsoft Teams, gerencie a criptografia de ponta a ponta usando o centro de administração do Teams e o Microsoft PowerShell.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- purview-compliance
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3e0d47107771add6e091afeeddc35d47110d7938
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614634"
---
# <a name="use-end-to-end-encryption-for-one-to-one-microsoft-teams-calls"></a>Use criptografia de ponta a ponta para chamadas um-para-um do Microsoft Teams

> [!IMPORTANT]
> O modelo de serviço do Teams e seu suporte à criptografia estão sujeitos a alterações para melhorar as experiências do cliente. Por exemplo, o serviço substitui regularmente os conjuntos de codificação que não são mais considerados seguros. Quaisquer alterações são feitas com a meta de manter o Teams seguro e confiável por padrão. Além disso, todo o conteúdo do cliente nos data centers da Microsoft é criptografado. Para obter informações sobre camadas de criptografia no Microsoft 365, consulte [Criptografia no Microsoft 365](/microsoft-365/compliance/encryption).

A criptografia de ponta a ponta, ou E2EE, ocorre quando o conteúdo é criptografado antes de ser enviado e descriptografado somente pelo destinatário pretendido. Com a criptografia de ponta a ponta, somente os dois sistemas de ponto de extremidade estão envolvidos na criptografia e na descriptografia dos dados de chamada. Nenhum outro grupo, incluindo a Microsoft, tem acesso à conversa descriptografada.

Com o E2EE para chamadas um-para-um não agendadas, somente o fluxo de mídia em tempo real, ou seja, os dados de voz e vídeo, para chamadas um-para-um do Teams criptografadas de ponta a ponta. Ambas as partes devem ativar essa configuração para habilitar a criptografia de ponta a ponta. [Criptografia no Microsoft 365](/microsoft-365/compliance/encryption) protege o chat, o compartilhamento de arquivos, a presença e outros conteúdos na chamada.

As chamadas criptografadas de ponta a ponta podem ser feitas entre duas partes quando: as partes estão usando a versão mais recente do cliente da área de trabalho do Teams para Windows ou Mac, estão em um dispositivo móvel com a atualização mais recente para iOS e Android ou estão em um Salas do Teams no dispositivo Windows usando a atualização mais recente.

Se você não habilitar a criptografia de ponta a ponta, o Teams ainda protegerá uma chamada ou reunião usando criptografia com base em padrões do setor. Os dados trocados durante as chamadas são sempre seguros em trânsito e em repouso. Para obter mais informações, consulte [Criptografia de mídia para o Teams](teams-security-guide.md#media-encryption).

Durante uma chamada criptografada de ponta a ponta, o Teams protege os seguintes recursos:

- Áudio

- Vídeo

- Compartilhamento de tela

Os seguintes recursos avançados não estão disponíveis durante uma chamada E2EE:

- Legendas ao vivo e transcrição

- Transferência de chamadas

- Mesclagem de chamadas

- Estacionamento de chamada

- Consultar e transferir

- Chame o complemento e transfira para outro dispositivo

- Adicionando um participante

- Gravando

Além disso, se sua organização usar a gravação de conformidade, a criptografia de ponta a ponta não estará disponível. Para obter mais informações sobre como o Teams dá suporte à gravação de conformidade, consulte [Introdução à gravação baseada em políticas do Teams para chamadas e reuniões](teams-recording-policy.md).

## <a name="configure-end-to-end-encryption-for-microsoft-teams"></a>Configurar criptografia de ponta a ponta para o Microsoft Teams

Conclua essas tarefas para que os usuários possam fazer chamadas criptografadas de ponta a ponta.

- Habilite a criptografia de ponta a ponta para sua organização criando uma ou mais políticas que definem quem pode usar a criptografia de ponta a ponta. Antes de começar, verifique se sua conta corporativa ou de estudante recebeu a função de administrador global ou do Teams. Para obter informações, consulte [Usar funções de administrador do Microsoft Teams para gerenciar o Teams](using-admin-roles.md). Quando estiver pronto para configurar o E2EE, você poderá usar o centro de administração do Teams ou o Microsoft PowerShell.

- Ative chamadas criptografadas de ponta a ponta nas configurações do Teams em seu dispositivo. Cada usuário precisa concluir essa tarefa, mas só precisa fazer isso em um dispositivo. O Teams sincroniza essa configuração entre os pontos de extremidade com suporte para cada usuário. Para obter instruções, consulte [Usar criptografia de ponta a ponta para chamadas do Teams](https://support.microsoft.com/office/1274b4d2-b5c5-4b24-a376-606fa6728a90).

### <a name="use-the-teams-admin-center-to-configure-end-to-end-encryption"></a>Usar o centro de administração do Teams para configurar a criptografia de ponta a ponta

A política padrão global, em toda a organização, especifica que a criptografia de ponta a ponta está desabilitada. Os usuários da sua organização terão automaticamente a política global, a menos que você crie e atribua uma política personalizada. Para habilitar a criptografia de ponta a ponta, crie uma nova política de criptografia ou modifique a política padrão global. Para habilitar a criptografia de ponta a ponta usando o Centro de administração do Teams, conclua estas etapas.

1. Usando uma conta corporativa ou de estudante que recebeu a função de administrador global ou do Teams, entre no [Centro de administração do Teams](https://admin.teams.microsoft.com/).

2. Vá para **Políticas de criptografia aprimoradas**.

3. Escolha a política padrão ou escolha **Adicionar** para adicionar uma nova política e nomeie a nova política.

4. Para habilitar a criptografia de ponta a ponta para seus usuários, para criptografia de chamada de ponta a **ponta, escolha** Não habilitado **,** mas os usuários podem habilitar e, em seguida, **escolher Salvar**.

   Para desabilitar a criptografia de ponta a ponta, escolha **Não habilitado**.

Depois de concluir a configuração da política, atribua a política a usuários, grupos ou todo o locatário da mesma maneira que gerencia outras políticas do Teams. Para obter informações sobre como usar políticas no Teams, consulte [Gerenciar o Teams com políticas](manage-teams-with-policies.md).

### <a name="use-microsoft-powershell-to-configure-end-to-end-encryption"></a>Usar o Microsoft PowerShell para configurar a criptografia de ponta a ponta

Você pode gerenciar políticas de criptografia de ponta a ponta usando o Microsoft PowerShell e o centro de administração do Teams. Vários cmdlets de criptografia de ponta a ponta estão incluídos no módulo PowerShell do Teams e documentados na [referência de cmdlet do Microsoft Teams](/powershell/teams/?view=teams-ps&preserve-view=true). Este artigo lista os cmdlets que você pode usar e fornece configurações de exemplo simples. Essas configurações usam a política global padrão. Sua organização pode exigir uma configuração de política mais complexa. Informações completas sobre esses cmdlets são fornecidas na referência de cmdlet.

Cmdlets do PowerShell de criptografia de ponta a ponta:

- [Get-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Get-CsTeamsEnhancedEncryptionPolicy) retorna informações sobre as políticas de criptografia aprimoradas do Teams em sua organização.

- [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) atribui e cancela a atribuição de políticas de criptografia avançada existentes a um usuário. Use `$NULL` para cancelar a atribuição de todas as políticas de um usuário.

- [New-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/New-CsTeamsEnhancedEncryptionPolicy) cria uma nova política de criptografia aprimorada do Teams.

- [Remove-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Remove-CsTeamsEnhancedEncryptionPolicy) exclui uma política de criptografia aprimorada da sua organização. Não é possível excluir a política global padrão.

- [Set-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Set-CsTeamsEnhancedEncryptionPolicy) atualiza valores em uma política de criptografia aprimorada existente do Teams.

Sua conta corporativa ou de estudante precisa da função de administrador global ou do Teams para configurar a criptografia de ponta a ponta.

#### <a name="to-enable-end-to-end-encryption-for-your-entire-tenant-using-the-global-policy"></a>Para habilitar a criptografia de ponta a ponta para todo o locatário usando a política global

By default, end-to-end encryption is disabled. To enable end-to-end encryption for the entire tenant by setting the default global policy, run the [Set-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Set-CsTeamsEnhancedEncryptionPolicy) cmdlet as follows.

```powershell
Set-CsTeamsEnhancedEncryptionPolicy -Identity Global -CallingEndtoEndEncryptionEnabledType DisabledUserOverride
```

Onde:

- `Global` indica que você está definindo essa configuração na política padrão global e em toda a organização.

- `DisabledUserOverride` indica que o E2EE está desabilitado no Teams por padrão, mas os usuários podem substituir o padrão e ativar o E2EE em suas configurações do Teams.

#### <a name="to-disable-end-to-end-encryption-for-your-entire-tenant-using-the-global-policy"></a>Para desabilitar a criptografia de ponta a ponta para todo o locatário usando a política global

By default, end-to-end encryption is disabled. If you've made changes to the global policy, you can change the setting back by running the [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) cmdlet as follows.

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity Global -CallingEndtoEndEncryptionEnabledType Disabled
```

Onde:

- `Global` indica que você está definindo essa configuração na política padrão global e em toda a organização.

- `Disabled` indica que você está desabilitando o E2EE para todos e os usuários não podem ativá-lo nas configurações do Teams.

#### <a name="to-enable-end-to-end-encryption-for-a-single-user"></a>Para habilitar a criptografia de ponta a ponta para um único usuário

Para habilitar a criptografia de ponta a ponta para um usuário, execute o cmdlet [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) da seguinte maneira.

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity "username" -PolicyName "policyname"
```

Onde:

- *`username`* é o nome do usuário.

- *`policyname`* é o nome que você deseja usar para a política. Os nomes de política não podem conter espaços, por exemplo, ContosoE2EEUserPolicy.

Users still need to switch on end-to-end encrypted calling in their Teams settings before they can make an end-to-end encrypted call. For instructions, see [Use end-to-end encryption for Teams calls](https://support.microsoft.com/office/1274b4d2-b5c5-4b24-a376-606fa6728a90).

Por exemplo:

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity "kenmeyer@contoso.onmicrosoft.com" -PolicyName "ContosoE2EEUserPolicy"
```

#### <a name="to-unassign-an-end-to-end-encryption-policy-from-a-single-user"></a>Para cancelar a atribuição de uma política de criptografia de ponta a ponta de um único usuário

Os usuários podem ter uma e apenas uma política de criptografia atribuída a eles por vez. Quando você cancela a atribuição de uma política de um usuário, o usuário recebe a política padrão global, em toda a organização. Não é possível cancelar a atribuição da política padrão. Para cancelar a atribuição de uma política de criptografia de ponta a ponta de um usuário, execute o cmdlet [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) da seguinte maneira.

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity "kenmeyer@contoso.onmicrosoft.com" -PolicyName $NULL
```

## <a name="switch-on-end-to-end-encryption-on-your-device"></a>Ativar criptografia de ponta a ponta em seu dispositivo

Para obter instruções, consulte [Usar criptografia de ponta a ponta para chamadas do Teams](https://support.microsoft.com/office/1274b4d2-b5c5-4b24-a376-606fa6728a90).

## <a name="related-topics"></a>Tópicos relacionados

[As 12 principais tarefas para as equipes de segurança dar suporte ao trabalho em casa](/microsoft-365/security/top-security-tasks-for-remote-work)

[Gerenciar configurações de reunião no Microsoft Teams](./meeting-settings-in-teams.md)
