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
description: Saiba mais sobre Roteamento Direto, como configuração, decisões de implantação principais necessárias e considerações de roteamento de voz.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: b378ee327f2ba284a348ff7458c617fed71541c6
ms.sourcegitcommit: 12044ab8b2e79a7b23bf9a0918ae070925d21f3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2021
ms.locfileid: "61401885"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a>Aparelho de Filial Desavivável (SBA) para Roteamento Direto


Ocasionalmente, um site do cliente que usa Roteamento Direto para se conectar ao Telefone Microsoft System pode ter uma paralisação na Internet.

Suponha que o site do cliente , chamado de filial, temporariamente não possa se conectar à nuvem da Microsoft por meio do Roteamento Direto. No entanto, a intranet dentro da filial ainda está totalmente funcional e os usuários podem se conectar ao Controlador de Borda de Sessão (SBC) que está fornecendo conectividade PSTN.

Este artigo descreve como usar um Aparelho de Filial Desavivável (SBA) para permitir que o sistema Telefone Microsoft continue a fazer e receber chamadas PSTN (Rede Telefônica Pública Comutado) no caso de uma paralisação.

## <a name="prerequisites"></a>Pré-requisitos

O SBA é um código distribuível fornecido pela Microsoft para fornecedores SBC que, em seguida, incorporam código em seu firmware ou o distribuem separadamente para que o SBA seja executado em uma VM ou hardware separado. 

Para obter o firmware mais recente do Controlador de Borda de Sessão com o Aparelho de Filial Suportável incorporado, entre em contato com o fornecedor SBC. Além disso, o seguinte é necessário:

- O SBC precisa ser configurado para Bypass de Mídia para garantir que o cliente Microsoft Teams no site de filial possa ter a mídia fluindo diretamente com o SBC. 

- O TLS1.2 deve estar habilitado no sistema operacional VM do SBA.
- As portas 3443, 4444 e 8443 são usadas pelo Microsoft SBA Server para se comunicar com o cliente Teams e devem ser permitidas no firewall. 
- A porta 5061 (ou a configurada no SBC) é usada pelo Microsoft SBA Server para se comunicar com o SBC e deve ser permitida no firewall. 
- A Porta UDP 123 é usada pelo Microsoft SBA Server para se comunicar com o servidor NTP e deve ser permitida no firewall.
- A porta 443 é usada pelo Microsoft SBA Server para se comunicar com Microsoft 365 e deve ser permitida no firewall.
- Os Intervalos ip do Azure e marcas de serviço para a Nuvem Pública devem ser definidos de acordo com as diretrizes descritas em: https://www.microsoft.com/download/details.aspx?id=56519

## <a name="supported-teams-clients"></a>Clientes Teams com suporte

O recurso SBA é suportado nos seguintes clientes Microsoft Teams: 

- Microsoft Teams Windows desktop 

- Microsoft Teams macOS desktop
- Teams mobile 
- Teams Telefones

## <a name="how-it-works"></a>Como funciona

Durante uma interrupção na Internet, Teams cliente deve alternar para o SBA automaticamente e as chamadas em andamento devem continuar sem interrupções. Nenhuma ação é necessária do usuário. Assim que o cliente Teams detectar que a Internet está em funcionamento e todas as chamadas de saída são concluídas, o cliente retornará ao modo de operação normal e se conectará a outros serviços Teams serviços. O SBA carregará registros de dados de chamada coletados na nuvem e o histórico de chamada será atualizado para que essas informações sejam disponibilizadas para revisão pelo administrador do locatário. 

Quando o Microsoft Teams cliente está no modo offline, a seguinte funcionalidade relacionada a chamada está disponível: 

- Fazendo chamadas PSTN via SBA/SBC local com a mídia fluindo através do SBC.

- Receber chamadas PSTN por meio de SBA/SBC local com mídia fluindo pelo SBC. 

- Espera e retomada de chamadas PSTN.

## <a name="configuration"></a>Configuração

Para que o recurso SBA funcione, o cliente Teams precisa saber quais SBAs estão disponíveis em cada site de filial e quais SBAs são atribuídos aos usuários nesse site. As etapas de configuração são as seguintes:

1. Crie os SBAs.
2. Crie a Teams de sobrevivência de filial.
3. Atribua a política aos usuários.
4. Registre um aplicativo para o SBA com Azure Active Directory.

Toda a configuração é feita usando Skype for Business cmdlets do PowerShell Online. (O Teams de administração do Teams ainda não dá suporte ao recurso SBA de Roteamento Direto.) 

(Para obter informações sobre como configurar o SBC, com links para a documentação do fornecedor SBC, consulte Session Border Controller configuration at the end of this article.)

### <a name="create-the-sbas"></a>Criar os SBAs

Para criar os SBAs, você usará o cmdlet New-CsTeamsSurvivableBranchAppliance. Este cmdlet tem os seguintes parâmetros:

| Parâmetro| Descrição |
| :------------|:-------|
| Identidade  | A identidade do SBA  |
| Fqdn | O FQDN do SBA |
| Site | TenantNetworkSite onde o SBA está localizado |
| Descrição | Texto de formato livre |
|||

Por exemplo:

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>Criar a política Teams de sobrevivência de filial 

Para criar uma política, use o cmdlet New-CsTeamsSurvivableBranchAppliancePolicy. Este cmdlet tem os seguintes parâmetros. Observe que a política pode conter um ou mais SBAs.

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

Você pode adicionar ou remover SBAs de uma política usando o cmdlet Set-CsTeamsSurvivableBranchAppliancePolicy. Por exemplo: 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>Atribuir uma política a um usuário

Para atribuir a política a usuários individuais, você usará o cmdlet Grant-CsTeamsSurvivableBranchAppliancePolicy usuário. Este cmdlet tem os seguintes parâmetros:

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

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>Registrar um aplicativo para o SBA com Azure Active Directory

Para permitir que diferentes SBAs usados em seu locatário leiam os dados necessários do Microsoft 365, você precisa registrar um aplicativo para o SBA com Azure Active Directory. 

Para obter mais informações sobre o registro do aplicativo, consulte o seguinte:

- [Desenvolver aplicativos de linha de negócios para Azure Active Directory](/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [Registre um aplicativo com o plataforma de identidade da Microsoft](/azure/active-directory/develop/quickstart-register-app).  

Você só precisa registrar um aplicativo para uso por todos os SBAs em seu locatário. 

Para o registro do SBA, você precisa dos seguintes valores criados pelo registro: 

- ID do aplicativo (cliente) 
- Segredo do cliente 

Para o aplicativo SBA, lembre-se do seguinte: 

- O nome pode ser o que você decidir.  
- Tipos de conta com suporte = Conta somente neste diretório organizacional. 
- O Uri de Redirecionamento da Web = https://login.microsoftonline.com/common/oauth2/nativeclient .
- Tokens de concessão implícitos = tokens de acesso e tokens de ID. 
- Permissões de API = Skype e Teams acesso de administrador de locatário -> Permissões de aplicativo -> application_access_custom_sba_appliance.
- Segredo do cliente: você pode usar qualquer descrição e expiração. 
- Lembre-se de copiar o segredo do cliente imediatamente após a criação. 
- A ID do aplicativo (cliente) é mostrada na guia Visão geral.

Em seguida, siga estas etapas:

1. Registre o aplicativo.
2. De definir os tokens de concessão implícitos.
3. De definir as permissões da API.
4. Crie o segredo do cliente.


## <a name="session-border-controller-configuration"></a>Configuração do Controlador de Borda de Sessão 

Para obter orientações passo a passo sobre como configurar o Controlador de Borda de Sessão com o Aparelho de Filial Suportável incorporado, consulte a documentação fornecida pelo fornecedor SBC: 

- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [Faixa de Opções](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-Systems](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>Problemas de relatórios

Reporte quaisquer problemas à organização de suporte do fornecedor SBC. Ao relatar o problema, indique que você tem um Aparelho de Filial Desavivável configurado.

## <a name="known-issues"></a>Problemas conhecidos

- Quando você adiciona novos Aparelhos de Filial Desavisáveis, pode levar algum tempo até que você possa usá-los em políticas de Aparelho de Filial Suportável.

- Quando você atribui uma política de Aparelho de Filial Desavivável a um usuário, pode levar algum tempo até que o SBA seja mostrado na saída de Get-CsOnlineUser. 

- A inversão de número em contatos do Azure AD não é realizada. 

- O SBA não dá suporte às configurações de encaminhamento de chamada. 

- Não há suporte para fazer uma chamada de emergência para um número de emergência configurado para chamada de emergência dinâmica (E911).
