---
title: Encaminhamento direto SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/08/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Saiba mais sobre roteamento direto, como configuração, decisões de implantação básica necessárias e considerações de roteamento de voz.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3204bc58b083f62feca3f878d2189558b69af6bd
ms.sourcegitcommit: 6b24c82837ca2c11f450a162ca4fab3dfa4ac8d4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620720"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing---public-preview"></a>Aplicativo de ramificação sobreviventes (SBA) para roteamento direto-visualização pública


> [!NOTE]
> Esta é uma versão de visualização pública.

Às vezes, um site do cliente que usa o roteamento direto para se conectar ao sistema telefônico da Microsoft pode sofrer uma falha na Internet.

Suponha que o site do cliente--chamado de ramificação--temporariamente não pode se conectar ao Microsoft Cloud por meio do roteamento direto. No entanto, a intranet dentro da ramificação ainda é totalmente funcional e os usuários podem se conectar ao controlador de borda de sessão (SBC) que está fornecendo conectividade PSTN.

Este artigo descreve como usar um aparelho de ramificação sobreviventes (SBA) para permitir que o sistema de telefonia da Microsoft continue a fazer e receber chamadas de rede telefônica pública comutada (PSTN) no caso de uma paralisação.

## <a name="prerequisites"></a>Pré-requisitos

O SBA é um código distribuível fornecido pela Microsoft a fornecedores SBC que, em seguida, insere código em seu firmware ou distribui-lo separadamente para ter o SBA executado em uma VM ou em um hardware separado. 

Para obter o firmware do controlador de borda de sessão mais recente com o aparelho de ramificação sobreviventes incorporado, entre em contato com o fornecedor do SBC. Além disso, é necessário o seguinte:

- O SBC precisa ser configurado para bypass de mídia para garantir que o cliente do Microsoft Teams no site de ramificação possa ter mídia que flui diretamente com o SBC. 

- O TLS 1.2 deve ser habilitado no sistema operacional VM SBA.

## <a name="supported-teams-clients"></a>Clientes de equipes com suporte

O recurso SBA tem suporte nos seguintes clientes do Microsoft Teams: 

- Microsoft Teams Windows Desktop 

- Área de trabalho do macOS do Microsoft Teams 

## <a name="how-it-works"></a>Como funciona

Durante uma falha na Internet, o cliente da equipe deve alternar para o SBA automaticamente, e as chamadas contínuas devem continuar sem interrupções. Nenhuma ação é necessária do usuário. Assim que o cliente do teams detectar que a Internet está ativa e todas as chamadas feitas terminarem, o cliente retornará ao modo de operação normal e se conectará a outros serviços do teams. O SBA carregará os registros de dados de chamadas coletados para a nuvem e o histórico de chamadas será atualizado para que essas informações estejam disponíveis para análise pelo administrador do locatário. 

Quando o cliente do Microsoft Teams está no modo offline, a seguinte funcionalidade relacionada a chamadas está disponível: 

- Realização de chamadas PSTN via SBA/SBC locais com mídia fluindo pelo SBC.

- Recebimento de chamadas PSTN via SBA/SBC locais com mídia fluindo pelo SBC. 

- Espera e retomada de chamadas PSTN.

## <a name="configuration"></a>Configuração

Para que o recurso SBA funcione, o cliente das equipes precisa saber quais SBAs estão disponíveis em cada site de filial e quais SBAs são atribuídos aos usuários desse site. As etapas de configuração são as seguintes:

1. Crie o SBAs.
2. Criar a política de sustentabilidade da ramificação do teams.
3. Atribua a política aos usuários.
4. Registre um aplicativo para o SBA com o Azure Active Directory.

Todas as configurações são feitas usando cmdlets do PowerShell do Skype for Business online. (O centro de administração do teams ainda não é compatível com o recurso de roteamento direto SBA.) 

(Para obter informações sobre como configurar o SBC, com links para a documentação do fornecedor do SBC, consulte configuração do controlador de borda de sessão no final deste artigo.)

### <a name="create-the-sbas"></a>Criar a SBAs

Para criar o SBAs, você vai usar o cmdlet New-CsTeamsSurvivableBranchAppliance. Este cmdlet tem os seguintes parâmetros:

| Parâmetro| Descrição |
| :------------|:-------|
| Identidade  | A identidade do SBA  |
| Fqdn | O FQDN do SBA |
| Site | O TenantNetworkSite em que o SBA está localizado |
| Descrição | Texto em formato livre |
|||

Por exemplo:

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>Criar a política de sustentabilidade da ramificação do teams 

Para criar uma política, use o cmdlet New-CsTeamsSurvivableBranchAppliancePolicy. Esse cmdlet tem os parâmetros a seguir. Observe que a política pode conter um ou mais SBAs.

| Parâmetro| Descrição |
| :------------|:-------|
| Identidade | A identidade da política |
| BranchApplianceFqdns  | O FQDN do (s) SBA (s) no site |
||

Por exemplo:

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

Você pode adicionar ou remover SBAs de uma política usando o cmdlet Set-CsTeamsSurvivableBranchAppliancePolicy. Por exemplo: 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>Atribuir uma política a um usuário

Para atribuir a política a usuários individuais, você vai usar o cmdlet Grant-CsTeamsSurvivableBranchAppliancePolicy. Esse cmdlet tem os seguintes parâmetros:

| Parâmetro| Descrição |
| :------------|:-------|
| Identidade | A identidade do usuário |
| PolicyName | A identidade da política |
||

Por exemplo:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

Você pode remover uma política de um usuário concedendo a política de $Null conforme mostrado no próximo exemplo:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>Registrar um aplicativo para o SBA com o Azure Active Directory

Para permitir que diferentes SBAs usadas dentro do seu locatário leiam os dados necessários do Microsoft 365, você precisa registrar um aplicativo para o SBA com o Azure Active Directory. 

Para obter mais informações sobre o registro do aplicativo, consulte o seguinte:

- [Desenvolver aplicativos de linha de negócios para o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [Registre um aplicativo com a plataforma de identidade da Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).  

Você só precisa registrar um aplicativo para uso por todos os SBAs em seu locatário. 

Para o registro SBA, você precisa dos seguintes valores criados pelo registro: 

- ID do aplicativo (cliente) 
- Segredo do cliente 

Para o aplicativo SBA, tenha em mente o seguinte: 

- O nome pode ser qualquer coisa que você decidir.  
- Tipos de conta com suporte = conta neste diretório organizacional apenas. 
- O URI de redirecionamento da Web = https://login.microsoftonline.com/common/oauth2/nativeclient .
- Símbolos de concessão implícito = tokens de acesso e tokens de identificação. 
- Permissões de API = acesso de administrador de locatários do Skype e do teams-> permissões de aplicativo-> application_access_custom_sba_appliance.
- Segredo do cliente: você pode usar qualquer descrição e expiração. 
- Lembre-se de copiar o segredo do cliente imediatamente após criá-lo. 
- A ID do aplicativo (cliente) é mostrada na guia Visão geral.

Siga estas etapas:

1. Registre o aplicativo.
2. Defina os tokens de concessão implícito.
3. Defina as permissões da API.
4. Crie o segredo do cliente.


## <a name="session-border-controller-configuration"></a>Configuração de controlador de borda de sessão 

Para obter uma orientação passo a passo sobre como configurar o controlador de borda de sessão com o dispositivo de ramificação sobreviventes incorporado, consulte a documentação fornecida pelo seu fornecedor de SBC: 

- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [Faixa](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [SMS-Systems](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>Relatar problemas

Relatar problemas à organização de suporte de seu fornecedor de SBC. Ao relatar o problema, indique que você tem um aparelho de ramificação sobreviventes configurado.

## <a name="known-issues"></a>Problemas conhecidos

- Ao adicionar novos aparelhos de ramificação sobreviventes, pode levar algum tempo até que você possa usá-los em políticas de aparelho de ramificação sobreviventes.

- Ao atribuir uma política de aparelho de ramificação sobreviventes a um usuário, pode levar algum tempo até que o SBA seja mostrado na saída de Get-CsOnlineUser. 

- A pesquisa de número reverso nos contatos do Azure AD não é realizada. 

- O SBA não é compatível com as configurações de encaminhamento de chamadas. 

- Não há suporte para fazer uma chamada de emergência para um número de emergência configurado para chamadas de emergência dinâmicas (E911).

- A saída de Get-CsOnlineUser mostra TeamsBranchSurvivabilityPolicy.
