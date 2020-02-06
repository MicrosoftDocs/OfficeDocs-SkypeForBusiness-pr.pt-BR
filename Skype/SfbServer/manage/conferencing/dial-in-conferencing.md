---
title: Gerenciar a conferência discada no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 85644a2d-7694-4573-8301-aa6490b43ff4
description: 'Resumo: saiba como gerenciar a conferência discada no Skype for Business Server.'
ms.openlocfilehash: ba8b62456a1fa2024f2cf37642658e76d528ebf3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818572"
---
# <a name="manage-dial-in-conferencing-in-skype-for-business-server"></a>Gerenciar a conferência discada no Skype for Business Server
 
**Resumo:** Saiba como gerenciar a conferência discada no Skype for Business Server.
  
Este tópico descreve como gerenciar conferência discada. Para obter mais informações sobre como planejar e configurar uma conferência discada na implantação, consulte [planejar a conferência discada no Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md) e [Configurar a conferência discada no Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
  
Você pode executar as seguintes tarefas para gerenciar a conferência discada: habilitar ou desabilitar a conferência discada, gerenciar números de acesso, gerenciar políticas de PIN para a conferência discada, gerenciar o ingresso em conferência e deixar anúncios, modificar mapeamentos de teclas para DTMF comandos e usuários da tela de boas-vindas para conferência discada. 
  
Para obter mais informações sobre como gerenciar planos de discagem, consulte [criar ou modificar um plano de discagem no Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
  
Para obter mais informações sobre o uso de PSTN, consulte [Configurar políticas de voz, registros de uso PSTN e rotas de voz no Skype for Business](../../deploy/deploy-enterprise-voice/voice-and-pstn.md).
  
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Gerenciar a conferência discada usando o painel de controle do Skype for Business Server

Para gerenciar informações sobre conferência discada:
  
1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2.  Abra o painel de controle do Skype for Business Server.
    
3. Na barra de navegação esquerda, clique em **Conferência**.
    
Para gerenciar informações sobre planos de discagem e uso PSTN:
  
1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2.  Abra o painel de controle do Skype for Business Server.
    
3. Na barra de navegação esquerda, clique em **Roteamento de Voz**.
    
## <a name="manage-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Gerenciar a conferência discada usando o Shell de gerenciamento do Skype for Business Server

Para gerenciar a conferência discada usando o Shell de gerenciamento do Skype for Business Server, use os seguintes cmdlets:
  
**Definições de configuração de discagem**

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Get-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Retorna informações sobre os diretórios de conferências configurados para uso em sua organização. Os diretórios de conferência são usados para ajudar usuários de conferência discada a localizar informações de conferência.  <br/> |
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Recupera informações sobre como o Skype for Business Server responde quando os usuários unem ou deixam uma conferência discada.  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Retorna informações sobre todos os números de acesso à conferência discada configurados para uso na organização.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Retorna as definições de sinalização DTMF (multifrequência de tom dual) utilizadas em conferências discadas. A DTMF permite que os usuários que discam para uma conferência controlem as definições da conferência (como ativar e desativar a Opção Mudo, ou bloquear e desbloquear a conferência) usando o teclado de seus telefones. ps-intro-in-LS2010  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Retorna uma lista de idiomas, incluindo idiomas regionais/minoritários, com suporte para uso com conferências discada do Skype for Business Server. Esses idiomas são usados para retransmitir mensagens de áudio e instruções a usuários que participam de uma conferência usando um telefone.  <br/> |
|[Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Retorna as informações sobre os planos de discagem utilizados na organização.  <br/> |
|[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Atribui um plano de discagem a um ou mais usuários ou grupos.  <br/> |
|[Import-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Importa diretórios de conferência do Microsoft Office Communications Server 2007 R2 para o Skype for Business Server. Isso ajuda a oferecer interoperabilidade entre o Skype for Business Server e o Office Communications Server 2007 R2.  <br/> |
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Transfere um diretório de conferência existente de um pool para outro.  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Cria um novo diretório de conferência para uso na organização.  <br/> |
|[New-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Cria um novo número de acesso de conferência discada.  <br/> |
|[New-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Cria uma nova coleção de definições de configuração de conferências discadas. Essas configurações determinam como o Skype for Business Server responde quando os usuários unem ou deixam uma conferência discada. Mais especificamente, são retornadas informações sobre a exigência feita aos participantes de registrarem ou não o seu nome ao entrar em uma conferência e como (ou se) o sistema anunciará que alguém entrou na chamada ou a abandonou.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)  <br/> |ria uma uma nova coleção de configurações de sinalização DTMF (multifrequência de tom dual) usada para conferência discada.  <br/> |
|[New-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Cria um novo plano de discagem.  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Remove um diretório de conferência existente.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Remove um número de acesso de conferência discada existente.  <br/> |
|[Remove-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Remove uma ou mais coleções das definições de configuração da conferência discada. Essas configurações determinam como o Skype for Business Server responde quando os usuários unem ou deixam uma conferência discada.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Remove uma coleção existente de definições de sinalização DTMF (multifrequência de tom dual) usada para conferência discada.  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Modifica os valores da propriedade de um número de acesso de conferência discada existente.  <br/> |
|[Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |Modifica as configurações que determinam como o Skype for Business Server responde quando os usuários unem ou deixam uma conferência discada.  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Modifica as definições de sinalização DTMF (multifrequência de tom dual) utilizadas em conferências discadas.  <br/> |
|[Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |Modifica um plano de discagem existente.  <br/> |
   
**Configurações de política de PIN**

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |Retorna informações sobre as diretivas de PIN do cliente configuradas para uso na organização. A autenticação de PIN permite que os usuários acessem o Skype for Business Server fornecendo um PIN em vez de um nome de usuário e senha.  <br/> |
|[Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |Atribui um número de identificação pessoal (PIN) de cliente a um usuário ou grupo de usuários.  <br/> |
|[New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |Cria uma nova política de número de identificação pessoal (PIN) do cliente.  <br/> |
|[Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |Remove a diretiva de PIN especificada.  <br/> |
|[Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |Modifica uma ou várias políticas existentes de números de identificação pessoal (PINs) de cliente.  <br/> |
   

