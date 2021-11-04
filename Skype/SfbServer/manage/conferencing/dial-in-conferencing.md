---
title: Gerenciar conferência discagem no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 85644a2d-7694-4573-8301-aa6490b43ff4
description: 'Resumo: saiba como gerenciar a conferência discagem no Skype for Business Server.'
ms.openlocfilehash: 3c6f72d3e2c5e19ef970e7d8e5410dcc9cad2d14
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60772057"
---
# <a name="manage-dial-in-conferencing-in-skype-for-business-server"></a>Gerenciar conferência discagem no Skype for Business Server
 
**Resumo:** Saiba como gerenciar a conferência discagem em Skype for Business Server.
  
Este tópico descreve como gerenciar a conferência discagem. Para obter mais informações sobre como planejar e configurar a conferência discda na implantação, consulte [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md) and Configure [dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
  
Você pode executar as seguintes tarefas para gerenciar a conferência discagem: habilitar ou desabilitar a conferência discado, gerenciar números de acesso, gerenciar políticas de PIN para discagem em conferência, gerenciar comunicados de entrada e saída de conferência, modificar mapeamentos de chaves para comandos DTMF e dar boas-vindas aos usuários para conferência discar. 
  
Para obter mais informações sobre como gerenciar planos de discagem, consulte [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
  
Para obter mais informações sobre o uso de PSTN, consulte [Configure voice policies, PSTN usage records, and voice routes in Skype for Business](../../deploy/deploy-enterprise-voice/voice-and-pstn.md).
  
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Gerenciar conferência discada usando o painel Skype for Business Server Controle

Para gerenciar informações sobre conferência discagem:
  
1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2.  Abra Skype for Business Server Painel de Controle.
    
3. Na barra de navegação esquerda, clique em **Conferência**.
    
Para gerenciar informações sobre planos de discagem e uso PSTN:
  
1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2.  Abra Skype for Business Server Painel de Controle.
    
3. Na barra de navegação esquerda, clique em **Roteamento de voz**.
    
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Gerenciar conferência discada usando o Shell de Gerenciamento Skype for Business Server Gerenciamento

Para gerenciar a conferência discada usando Skype for Business Server Shell de Gerenciamento, use os seguintes cmdlets:
  
**Configurações discar**

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Get-CsConferenceDirectory](/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Retorna informações sobre os diretórios de conferências configurados para uso na organização. Os diretórios de conferência são usados para ajudar usuários de conferência discada a localizar informações de conferência.  <br/> |
|[Get-CsDialInConferencingConfiguration](/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Recupera informações sobre como o Skype for Business Server responde quando os usuários ins juntam ou saem de uma conferência discagem.  <br/> |
|[Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Retorna informações sobre todos os números de acesso à conferência discada configurados para uso na organização.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Retorna as configurações de sinalização DTMF (multifrequência de tom duplo) usadas para conferência discada. A DTMF permite que os usuários que discam para uma conferência controlem as definições da conferência (como ativar e desativar o mudo, ou bloquear e desbloquear a conferência) usando o teclado de seus telefones.  <br/> |
|[Get-CsDialInConferencingLanguageList](/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Retorna uma lista de idiomas, incluindo idiomas regionais/minoritários, com suporte para uso com Skype for Business Server conferências discadas. Esses idiomas são usados para retransmitir mensagens de áudio e instruções a usuários que participam de uma conferência usando um telefone.  <br/> |
|[Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Retorna as informações sobre os planos de discagem utilizados na organização.  <br/> |
|[Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Atribui um plano de discagem a um ou mais usuários ou grupos.  <br/> |
|[Import-CsLegacyConferenceDirectory](/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Importa diretórios de conferência do Microsoft Office Communications Server 2007 R2 para Skype for Business Server. Isso ajuda a fornecer interoperabilidade entre Skype for Business Server e Office Communications Server 2007 R2.  <br/> |
|[Move-CsConferenceDirectory](/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Transfere um diretório de conferência existente de um pool para outro.  <br/> |
|[New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Cria um novo diretório de conferência para uso na organização.  <br/> |
|[New-CsDialInConferencingAccessNumber](/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Cria um novo número de acesso de conferência discada.  <br/> |
|[New-CsDialInConferencingConfiguration](/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Cria uma nova coleção de definições de configuração de conferências discadas. Essas configurações determinam como o Skype for Business Server responde quando os usuários ins juntam ou saem de uma conferência discagem. Mais especificamente, retornam-se informações sobre a exigência feita aos participantes de registrarem ou não o seu nome ao entrar em uma conferência e como (ou se) o sistema anunciará que alguém entrou na chamada ou a abandonou.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)  <br/> |Cria uma nova coleção de configurações de sinalização DTMF (dual-tone multi-frequency) usadas para conferência discada.  <br/> |
|[New-CsDialPlan](/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Cria um novo plano de discagem.  <br/> |
|[Remove-CsConferenceDirectory](/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Remove um diretório de conferência existente.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Remove um número de acesso de conferência discada.  <br/> |
|[Remove-CsDialInConferencingConfiguration](/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Remove uma ou mais coleções das definições de configuração da conferência discada. Essas configurações determinam como o Skype for Business Server responde quando os usuários ins juntam ou saem de uma conferência discagem.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Remove uma coleção existente de configurações de sinalização DTMF (dual-tone multi-frequency) usadas para conferência discada.  <br/> |
|[Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Modifica os valores da propriedade de um número de acesso de conferência discada existente.  <br/> |
|[Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |Modifica as configurações que determinam como Skype for Business Server responde quando os usuários ins juntam ou saem de uma conferência discagem.  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Modifica as definições de sinalização DTMF (multifrequência de tom dual) utilizadas em conferências discadas.  <br/> |
|[Set-CsDialPlan](/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |Modifica um plano de discagem existente.  <br/> |
   
**Configurações de política de PIN**

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |Retorna informações sobre as diretivas de PIN do cliente configuradas para uso na organização. A autenticação de PIN permite que os usuários acessem Skype for Business Server fornecendo um PIN em vez de um nome de usuário e senha.  <br/> |
|[Grant-CsPinPolicy](/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |Atribui um número de identificação pessoal (PIN) de cliente a um usuário ou grupo de usuários.  <br/> |
|[New-CsPinPolicy](/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |Cria uma nova política de número de identificação pessoal (PIN) do cliente.  <br/> |
|[Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |Remove a diretiva de PIN especificada.  <br/> |
|[Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |Modifica uma ou várias políticas existentes de números de identificação pessoal (PINs) de cliente.  <br/> |
