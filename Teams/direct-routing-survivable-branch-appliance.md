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
ms.openlocfilehash: 976c73aebe698152c4824e3eaedfcc19a13ae525
ms.sourcegitcommit: 1be178dc3b34575e1914e629f004f897c02e0097
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2022
ms.locfileid: "68138484"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a>SBA (Aparelho de Filial Persistente) para Roteamento Direto


Ocasionalmente, um site do cliente que usa o Roteamento Direto para se conectar ao Sistema de Telefonia da Microsoft pode ter uma interrupção na Internet.

Suponha que o site do cliente , chamado de branch, temporariamente não possa se conectar à nuvem da Microsoft por meio do Roteamento Direto. No entanto, a intranet dentro do branch ainda é totalmente funcional e os usuários podem se conectar ao Controlador de Borda de Sessão (SBC) que está fornecendo conectividade PSTN.

Este artigo descreve como usar um SBA (Aparelho de Filial Persistente) para permitir que o Sistema de Telefonia da Microsoft continue a fazer e receber chamadas PSTN (Rede Telefônica Pública Comucionável) em caso de interrupção.

## <a name="prerequisites"></a>Pré-requisitos

O SBA é um código distribuível fornecido pela Microsoft para fornecedores SBC que, em seguida, inseem código em seu firmware ou o distribuem separadamente para que o SBA seja executado em uma VM ou hardware separado. 

Para obter o firmware mais recente do Controlador de Borda de Sessão com o Aparelho de Filial Persistente inserido, entre em contato com o fornecedor do SBC. Além disso, o seguinte é necessário:

- O SBC precisa ser configurado para o Bypass de Mídia para garantir que o cliente do Microsoft Teams no site de filial possa ter mídia fluindo diretamente com o SBC. 

- O TLS1.2 deve ser habilitado no sistema operacional da VM do SBA.
- As portas 3443, 4444 e 8443 são usadas pelo Microsoft SBA Server para se comunicar com o cliente do Teams e devem ser permitidas no firewall. 
- A porta 5061 (ou a configurada no SBC) é usada pelo Microsoft SBA Server para se comunicar com o SBC e deve ser permitida no firewall. 
- A porta UDP 123 é usada pelo Microsoft SBA Server para se comunicar com o servidor NTP e deve ser permitida no firewall.
- A porta 443 é usada pelo Microsoft SBA Server para se comunicar com o Microsoft 365 e deve ser permitida no firewall.
- Os Intervalos de IP do Azure e as Marcas de Serviço para a Nuvem Pública devem ser definidos de acordo com as diretrizes descritas em: https://www.microsoft.com/download/details.aspx?id=56519

## <a name="supported-teams-clients"></a>Clientes do Teams com suporte

O recurso SBA tem suporte nos seguintes clientes do Microsoft Teams: 

- Área de trabalho do Windows do Microsoft Teams 

- Área de trabalho macOS do Microsoft Teams
- Teams para Dispositivos Móveis 
- Telefones do Teams

## <a name="how-it-works"></a>Como funciona

Durante uma interrupção na Internet, o cliente do Teams deve alternar automaticamente para o SBA e as chamadas em andamento devem continuar sem interrupções. Nenhuma ação é necessária do usuário. Assim que o cliente do Teams detectar que a Internet está ativo e todas as chamadas de saída forem concluídas, o cliente voltará ao modo de operação normal e se conectará a outros serviços do Teams. O SBA carregará registros de dados de chamada coletados para a nuvem e o histórico de chamadas será atualizado para que essas informações sejam disponibilizadas para revisão pelo administrador do locatário. 

Quando o cliente do Microsoft Teams está no modo offline, a seguinte funcionalidade relacionada à chamada está disponível: 

- Fazendo chamadas PSTN via SBA/SBC local com a mídia fluindo pelo SBC.

- Recebendo chamadas PSTN via SBA/SBC local com mídia fluindo pelo SBC. 

- Manter e retomar chamadas PSTN.

## <a name="configuration"></a>Configuração

Para que o recurso SBA funcione, o cliente do Teams precisa saber quais SBAs estão disponíveis em cada site de filial e quais SBAs são atribuídos aos usuários nesse site. As etapas de configuração são as seguintes:

1. Crie os SBAs.
2. Crie a política de sobrevivência do branch do Teams.
3. Atribua a política aos usuários.
4. Registre um aplicativo para o SBA com o Azure Active Directory.

Toda a configuração é feita usando Skype for Business cmdlets do PowerShell Online. (O Centro de administração do Teams ainda não dá suporte ao recurso SBA de Roteamento Direto.) 

(Para obter informações sobre como configurar o SBC, com links para a documentação do fornecedor SBC, consulte a configuração do Controlador de Borda de Sessão no final deste artigo.)

### <a name="create-the-sbas"></a>Criar os SBAs

Para criar os SBAs, você usará o New-CsTeamsSurvivableBranchAppliance cmdlet. Esse cmdlet tem os seguintes parâmetros:

| Parâmetro| Descrição |
| :------------|:-------|
| Identidade  | A identidade do SBA  |
| Fqdn | O FQDN do SBA |
| Site | O TenantNetworkSite onde o SBA está localizado |
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

### <a name="create-the-teams-branch-survivability-policy"></a>Criar a Política de Sobrevivência do Branch do Teams 

Para criar uma política, use o New-CsTeamsSurvivableBranchAppliancePolicy cmdlet. Esse cmdlet tem os seguintes parâmetros. Observe que a política pode conter um ou mais SBAs.

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

Você pode adicionar ou remover SBAs de uma política usando o Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet. Por exemplo: 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>Atribuir uma política a um usuário

Para atribuir a política a usuários individuais, você usará o cmdlet Grant-CsTeamsSurvivableBranchAppliancePolicy usuário. Esse cmdlet tem os seguintes parâmetros:

| Parâmetro| Descrição |
| :------------|:-------|
| Identidade | A identidade do usuário |
| Policyname | A identidade da política |
||

Por exemplo:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

Você pode remover uma política de um usuário concedendo a política de $Null, conforme mostrado no próximo exemplo:

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>Registrar um aplicativo para o SBA com o Azure Active Directory

Para permitir que diferentes SBAs usados em seu locatário leiam os dados necessários do Microsoft 365, você precisa registrar um aplicativo para o SBA com o Azure Active Directory. 

Para obter mais informações sobre o registro de aplicativo, consulte o seguinte:

- [Desenvolver aplicativos de linha de negócios para o Azure Active Directory](/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [Registre um aplicativo com o plataforma de identidade da Microsoft](/azure/active-directory/develop/quickstart-register-app).  

Você só precisa registrar um aplicativo para uso por todos os SBAs em seu locatário. 

Para o registro do SBA, você precisa dos seguintes valores criados pelo registro: 

- ID do aplicativo (cliente) 
- Segredo do cliente 

Para o aplicativo SBA, lembre-se do seguinte: 

- O nome pode ser o que você decidir.  
- Tipos de conta com suporte = Conta somente neste diretório organizacional. 
- O URI de Redirecionamento da Web = https://login.microsoftonline.com/common/oauth2/nativeclient.
- Tokens de concessão implícitos = tokens de acesso e tokens de ID. 
- Permissões de API = Permissões de Aplicativo Administração Acesso > Skype e Teams -> application_access_custom_sba_appliance.
- Segredo do cliente: você pode usar qualquer descrição e expiração. 
- Lembre-se de copiar o segredo do cliente imediatamente após criá-lo. 
- A ID do aplicativo (cliente) é mostrada na guia Visão geral.

Em seguida, siga estas etapas:

1. Registre o aplicativo.
2. Defina os tokens de concessão implícitos.
3. Defina as permissões de API.
4. Crie o segredo do cliente.


## <a name="session-border-controller-configuration"></a>Configuração do Controlador de Borda da Sessão 

Para obter diretrizes passo a passo sobre como configurar o Controlador de Borda de Sessão com o Aparelho de Filial Persistente inserido, consulte a documentação fornecida pelo fornecedor do SBC: 

- [AudioCodes](https://www.audiocodes.com/library/technical-documents?query=sba)

- [Faixa de Opções](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [Te-Systems](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>Relatar problemas

Relate quaisquer problemas à organização de suporte do fornecedor SBC. Ao relatar o problema, indique que você tem um Aparelho de Filial Persistente configurado.

## <a name="known-issues"></a>Problemas conhecidos

- Como o SBA depende de tokens de autenticação válidos por 24 horas e são renovados diariamente, atualmente o SBA pode dar suporte a interrupções por até 24 horas a partir da última autenticação. Isso significa que, se uma interrupção ocorrer 20 horas após a última renovação do token de autenticação, o SBA estará operacional somente nas 4 horas restantes.

- Quando você adiciona novos Aparelhos de Filial Persistentes, pode levar algum tempo até que você possa usá-los em políticas de Aparelho de Filial Persistente.

- Quando você atribui uma política de Aparelho de Filial Persistente a um usuário, pode levar algum tempo até que o SBA seja mostrado na saída de Get-CsOnlineUser. 

- A pesquisa inversa de número Azure AD contatos não é executada. 

- O SBA não dá suporte a configurações de encaminhamento de chamadas. 

- Não há suporte para fazer uma chamada de emergência para um número de emergência configurado para chamada de emergência dinâmica (E911).
