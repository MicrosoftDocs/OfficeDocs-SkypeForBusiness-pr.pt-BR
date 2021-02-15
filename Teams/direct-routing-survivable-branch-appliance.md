---
title: SBA de Roteamento Direto
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
description: Saiba mais sobre o Roteamento Direto, como configuração, decisões de implantação principais necessárias e considerações de roteamento de voz.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9fb8812fd025317eb9c6e3c67ce1f5fcea094978
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196485"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a>SBA (Dispositivo de Ramificação Sobrevável) para Roteamento Direto


Ocasionalmente, um site do cliente que usa Roteamento Direto para se conectar ao Microsoft Phone System pode ter uma queda na Internet.

Suponha que o site do cliente, chamado de ramificação, temporariamente não possa se conectar à nuvem da Microsoft por meio do Roteamento Direto. No entanto, a intranet dentro da ramificação ainda é totalmente funcional e os usuários podem se conectar ao Controlador de Borda de Sessão (SBC) que fornece conectividade PSTN.

Este artigo descreve como usar um SBA (Dispositivo de Ramificação Sobrevável) para permitir que o Microsoft Phone System continue a fazer e receber chamadas PSTN (Rede Telefônica Pública Comutado) no caso de uma paralisação.

## <a name="prerequisites"></a>Pré-requisitos

O SBA é um código distribuível fornecido pela Microsoft para fornecedores SBC que, em seguida, insemitem código em seu firmware ou o distribuem separadamente para que o SBA seja executado em um VM ou hardware separado. 

Para obter o firmware mais recente do Controlador de Borda de Sessão com o Dispositivo de Ramificação Sobrevável inserido, entre em contato com o fornecedor SBC. Além disso, é necessário fazer o seguinte:

- O SBC precisa ser configurado para o Bypass de Mídia para garantir que o cliente do Microsoft Teams no site de ramificação possa ter mídia fluindo diretamente com o SBC. 

- O TLS1.2 deve estar habilitado no sistema operacional VM SBA.

## <a name="supported-teams-clients"></a>Clientes do Teams com suporte

O recurso SBA tem suporte nos seguintes clientes do Microsoft Teams: 

- Área de trabalho do Microsoft Teams para Windows 

- Área de trabalho do Microsoft Teams macOS 

## <a name="how-it-works"></a>Como funciona

Durante uma interrupção na Internet, o cliente do Teams deve alternar para o SBA automaticamente e as chamadas em andamento devem continuar sem interrupções. Nenhuma ação é necessária do usuário. Assim que o cliente do Teams detectar que a Internet está pronta e todas as chamadas de saída terminarem, o cliente voltará ao modo de operação normal e se conectará a outros serviços do Teams. O SBA carregará registros de dados de chamada coletados na nuvem e o histórico de chamada será atualizado para que essas informações sejam disponibilizadas para revisão pelo administrador do locatário. 

Quando o cliente do Microsoft Teams está no modo offline, a seguinte funcionalidade relacionada a chamada está disponível: 

- Fazer chamadas PSTN via SBA/SBC local com mídia fluindo pelo SBC.

- Receber chamadas PSTN via SBA/SBC local com mídia fluindo pelo SBC. 

- Espera e Currículo de chamadas PSTN.

## <a name="configuration"></a>Configuração

Para que o recurso SBA funcione, o cliente do Teams precisa saber quais SBAs estão disponíveis em cada site de ramificação e quais SBAs são atribuídos aos usuários nesse site. As etapas de configuração são as seguintes:

1. Crie os SBAs.
2. Crie a política de sobreabilidade de ramificação do Teams.
3. Atribua a política aos usuários.
4. Registre um aplicativo para o SBA com o Azure Active Directory.

Toda a configuração é feita usando cmdlets do PowerShell do Skype for Business Online. (O Centro de administração do Teams ainda não dá suporte ao recurso SBA de Roteamento Direto.) 

(Para obter informações sobre como configurar o SBC, com links para a documentação do fornecedor SBC, consulte a configuração do Controlador de Borda de Sessão no final deste artigo.)

### <a name="create-the-sbas"></a>Criar os SBAs

Para criar os SBAs, você usará o cmdlet New-CsTeamsSurvivableBranchAppliance dados. Este cmdlet tem os seguintes parâmetros:

| Parâmetro| Descrição |
| :------------|:-------|
| Identidade  | A identidade do SBA  |
| Fqdn | O FQDN do SBA |
| Site | O TenantNetworkSite onde o SBA está localizado |
| Descrição | Formatar texto gratuito |
|||

Por exemplo:

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>Criar a Política de Surviabilidade de Ramificação do Teams 

Para criar uma política, use o cmdlet New-CsTeamsSurvivableBranchAppliancePolicy dados. Este cmdlet tem os seguintes parâmetros. Observe que a política pode conter um ou mais SBAs.

| Parâmetro| Descrição |
| :------------|:-------|
| Identidade | A identidade da política |
| BranchApplianceFqdns  | O FQDN dos SBA(s) no site |
||

Por exemplo:

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

Você pode adicionar ou remover SBAs de uma política usando o cmdlet Set-CsTeamsSurvivableBranchAppliancePolicy dados. Por exemplo: 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>Atribuir uma política a um usuário

Para atribuir a política a usuários individuais, você usará o cmdlet Grant-CsTeamsSurvivableBranchAppliancePolicy usuário. Este cmdlet tem os seguintes parâmetros:

| Parâmetro| Descrição |
| :------------|:-------|
| Identidade | A identidade do usuário |
| Policyname | A identidade da política |
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

Para permitir que diferentes SBAs usados em seu locatário leiam os dados necessários do Microsoft 365, você precisa registrar um aplicativo para o SBA com o Azure Active Directory. 

Para obter mais informações sobre o registro do aplicativo, consulte o seguinte:

- [Desenvolver aplicativos de linha de negócios para o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [Registre um aplicativo com a plataforma de identidade da Microsoft.](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)  

Você só precisa registrar um aplicativo para uso por todos os SBAs em seu locatário. 

Para o registro do SBA, você precisa dos seguintes valores criados pelo registro: 

- ID do aplicativo (cliente) 
- Segredo do cliente 

Para o aplicativo SBA, lembre-se do seguinte: 

- O nome pode ser o que você decidir.  
- Tipos de conta com suporte = Conta somente neste diretório organizacional. 
- O Uri de Redirecionamento da Web = https://login.microsoftonline.com/common/oauth2/nativeclient .
- Tokens de concessão implícitos = tokens do Access e tokens de ID. 
- Permissões de API = Acesso de Administrador de Locatários do Skype e do Teams > permissões de aplicativo -> application_access_custom_sba_appliance.
- Segredo do cliente: você pode usar qualquer descrição e expiração. 
- Lembre-se de copiar o segredo do cliente imediatamente após a criação. 
- A ID do Aplicativo (cliente) é mostrada na guia Visão Geral.

Em seguida, siga estas etapas:

1. Registre o aplicativo.
2. De definir os tokens implícitos de concessão.
3. Definir as permissões da API.
4. Crie o segredo do cliente.


## <a name="session-border-controller-configuration"></a>Configuração do Controlador de Borda de Sessão 

Para obter orientações passo a passo sobre como configurar o Controlador de Borda de Sessão com o Dispositivo de Ramificação Sobrevável inserido, consulte a documentação fornecida pelo fornecedor SBC: 

- [Audiocodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [Fita](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-Systems](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>Relatar problemas

Relatar problemas à organização de suporte do fornecedor SBC. Ao relatar o problema, indique que você configurou um Dispositivo de Ramificação Sobrevável.

## <a name="known-issues"></a>Problemas conhecidos

- Quando você adiciona novos Dispositivos de Ramificação Sobreváveis, pode levar algum tempo até que você possa usá-los nas políticas do Dispositivo de Ramificação Sobrevável.

- Quando você atribui uma política de Dispositivo de Ramificação Sobrevável a um usuário, pode levar algum tempo até que o SBA seja mostrado na saída do Get-CsOnlineUser. 

- A operação de inversão de número em Contatos do Azure AD não é executada. 

- O SBA não dá suporte às configurações de encaminhamento de chamada. 

- Não há suporte para fazer uma chamada de emergência para um número de emergência configurado para chamada de emergência dinâmica (E911).

- A saída do Get-CsOnlineUser mostra TeamsBranchSuráveisPolicy.
