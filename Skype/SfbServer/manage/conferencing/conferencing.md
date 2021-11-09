---
title: Gerenciar conferências em Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 825e051c-83a5-420d-a5ef-f77afa368e2e
description: 'Resumo: Saiba como gerenciar a conferência em Skype for Business Server.'
ms.openlocfilehash: 122b7d797983df9bb3ef6252234099869650a66e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845454"
---
# <a name="manage-conferencing-in-skype-for-business-server"></a>Gerenciar conferências em Skype for Business Server
 
**Resumo:** Saiba como gerenciar a conferência em Skype for Business Server.
  
Este tópico descreve como gerenciar a conferência. Para obter mais informações sobre como planejar e implantar conferências, consulte [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and Deploy [conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Em Skype for Business Server, você gerencia os detalhes da conferência especificando configurações e configurações de política da seguinte forma. Observe que as conferências e reuniões de termos às vezes são usadas de forma intercambiável. Mas, em geral, você pode pensar em uma reunião como uma instância específica de conferência.
  
- **As configurações** de política de conferência abrangem uma ampla variedade de opções de agendamento e participação, desde se uma reunião pode incluir áudio e vídeo IP até o número máximo de pessoas que podem participar. Você pode usar políticas de conferência para gerenciar a segurança, largura de banda e aspectos legais das reuniões.
    
    Observe que as políticas de conferência são aplicadas ao usuário ou site e não podem ser aplicadas a uma reunião específica. Portanto, o convite de reunião para a conferência pode ser criado com algumas semanas de antecedência, mas a política de conferência restritiva deve ser aplicada à conta de Skype for Business do Organizador da Reunião pouco antes do início da conferência. 
    
    Se uma conta dedicada for usada para a função Organizador da Reunião, a política de conferência poderá permanecer atribuída a essa conta. Se o Organizador da Reunião usar uma conta Skype for Business, a política deverá ser removida depois que a conferência for concluída.
    
- **As configurações de reunião** determinam o tipo de reuniões que os usuários podem criar, além de controlar como (ou mesmo se) usuários anônimos e usuários de conferência discada podem participar dessas reuniões. Observe que essas configurações afetam apenas reuniões agendadas. As configurações de reunião são aplicadas por pool, por site ou globalmente.
    
- **As configurações de conferência determinam** coisas como o tamanho máximo permitido para conteúdo de reunião e apostilas; quantidade máxima de largura de banda para o serviço de Conferência de Compartilhamento de Aplicativos; limites de armazenamento e períodos de expiração; as URLs para downloads internos e externos do cliente com suporte; ponteiros para URLs internas e externas onde os usuários podem obter ajuda e recursos de conferência; e as portas usadas para compartilhamento de aplicativos, áudio do cliente, transferências de arquivos e tráfego de mídia.
    
    Essas configurações permitem que você gerencie os servidores reais por conta própria. Essas configurações só podem ser definidas usando Skype for Business Server Shell de Gerenciamento. 
    
- **As configurações de acesso discado** permitem definir informações sobre se e como os usuários discam de um telefone. Você especifica algumas das informações de acesso discada, como número de acesso, da guia Conferência do Painel de Controle e algumas informações de discagem, como plano de discagem, política de voz, rota e uso de PSTN, na guia Roteamento de Voz do Painel de Controle.
    
- **As configurações de política de PIN** permitem que você nomee e defina o PIN que os participantes usam para acesso discado.
    
## <a name="manage-conferencing-by-using-skype-for-business-server-control-panel-or-by-using-skype-for-business-server-management-shell"></a>Gerenciar conferência usando o Painel de Controle Skype for Business Server ou usando Skype for Business Server Shell de Gerenciamento

Você pode gerenciar a maioria das políticas de conferência e configurações usando Skype for Business Server Painel de Controle ou usando Skype for Business Server Shell de Gerenciamento. Algumas configurações estão disponíveis somente usando o Shell de Gerenciamento Skype for Business Server Gerenciamento.
  
- Para gerenciar configurações de política de conferência:
    
  - No Painel de Controle, selecione **Conferência | Política de Conferência**.
    
  - No PowerShell, pesquise os cmdlets **-CsConferencingPolicy.**
    
- Para gerenciar as configurações de reunião:
    
  - No Painel de Controle, selecione **Conferência | Configuração de reunião**.
    
  - Em Skype for Business Server Shell de Gerenciamento, **pesquise os cmdlets -CsMeetingConfiguration.**
    
- Para gerenciar configurações de número de acesso discado:
    
  - No Painel de Controle, selecione **Conferência | Número de acesso discado**.
    
  - No Skype for Business Server De gerenciamento, pesquise os cmdlets **-CsDialInConferencing.**
    
- Para gerenciar informações de acesso discado, como plano de discagem, política de voz, rota e uso de PSTN: 
    
  - No Painel de Controle, selecione **Conferência | Roteamento de voz**.
    
  - Em Skype for Business Server Shell de Gerenciamento, pesquise os cmdlets **-CsDialPlan** e **-CsVoice.**
    
- Para gerenciar configurações de política de PIN:
    
  - No Painel de Controle, selecione **Conferência | Política pin**.
    
  - Em Skype for Business Server Shell de Gerenciamento, pesquise os cmdlets **-CsPinPolicy.**
    
- Para gerenciar as configurações de conferência, você deve usar o Shell Skype for Business Server Gerenciamento. Pesquise **cmdlets -CsConferencingConfiguration.**
    
## <a name="skype-for-business-server-management-shell-cmdlets"></a>Skype for Business Server Cmdlets do Shell de Gerenciamento

Você pode usar os seguintes cmdlets Skype for Business Server Shell de Gerenciamento para gerenciar a conferência: 
  
**Configurações de política de conferência**

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Get-CsConferencingPolicy](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Retorna informações sobre as diretivas de conferência que tenham sido configuradas para uso na organização. As diretivas de conferência determinam os recursos e capacidades que podem ser usados em uma conferência; isso inclui tudo, desde o fato de a conferência poder ou não incluir áudio e vídeo IP até o número máximo de pessoas que podem participar de uma reunião.  <br/> |
|[Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Atribui uma diretiva de conferência em escopo por usuário.  <br/> |
|[New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Cria uma nova política de conferência para uso na organização.  <br/> |
|[Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Remove a diretiva de conferência especificada.  <br/> |
|[Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Modifica uma diretiva de conferência existente.  <br/> |
   
**Definições de configuração de reunião**

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Retorna informações sobre as configurações de reunião atualmente em uso em sua organização. As configurações de reunião ajudam a ditar o tipo de reuniões que os usuários podem criar e controlar como (ou mesmo se) usuários anônimos e usuários de conferência discado podem participar dessas reuniões.  <br/> |
|[New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Cria um novo conjunto de configurações de reunião em escopo do local ou serviço. Observe que essas configurações afetam apenas reuniões agendadas; eles não afetam reuniões ad hoc criadas clicando na opção Reunir Agora em Skype for Business.  <br/> |
|[Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Exclui uma coleção existente de configurações de reunião.  <br/> |
|[Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Modifica as configurações de reunião atualmente em uso em sua organização.  <br/> |
   
**Configurações de conferência**

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Retorna informações sobre as definições de configuração de conferências da organização. As definições de conferências determinam aspectos como o tamanho máximo permitido do conteúdo e dos folhetos da conferência, o período de cortesia do conteúdo (ou seja, o tempo que o conteúdo será armazenado antes de ser excluído) e os URLs dos downloads internos e externos do cliente suportado.  <br/> |
|[New-CsConferencingConfiguration](/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Cria uma coleção definições de configuração de conferências.  <br/> |
|[Remove-CsConferencingConfiguration](/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Remove a coleção especificada de definições de configuração de conferências.  <br/> |
|[Set-CsConferencingConfiguration](/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Modifica um conjunto existente de definições de configuração de conferências.  <br/> |
   
**Configurações discar**

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Get-CsConferenceDirectory](/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Retorna informações sobre os diretórios de conferências configurados para uso na organização. Os diretórios de conferência são usados para ajudar usuários de conferência discada a localizar informações de conferência.  <br/> |
|[Get-CsDialInConferencingConfiguration](/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Recupera informações sobre como o Skype for Business Server responde quando os usuários ins juntam ou saem de uma conferência discagem.  <br/> |
|[Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Retorna informações sobre todos os números de acesso à conferência discada configurados para uso na organização.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Retorna as definições de sinalização DTMF (multifrequência de tom dual) utilizadas em conferências discadas. A DTMF permite que os usuários que discam para uma conferência controlem as definições da conferência (como ativar e desativar o mudo, ou bloquear e desbloquear a conferência) usando o teclado de seus telefones.  <br/> |
|[Get-CsDialInConferencingLanguageList](/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Retorna uma lista de idiomas, incluindo idiomas regionais/minoritários, com suporte para uso com Skype for Business Server conferências discadas. Esses idiomas são usados para retransmitir mensagens de áudio e instruções a usuários que participam de uma conferência usando um telefone.  <br/> |
|[Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Retorna as informações sobre os planos de discagem utilizados na organização.  <br/> |
|[Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Atribui um plano de discagem a um ou mais usuários ou grupos.  <br/> |
|[Import-CsLegacyConferenceDirectory](/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Importa diretórios de conferência do Microsoft Office Communications Server 2007 R2 para Skype for Business Server. Isso ajuda a fornecer interoperabilidade entre Skype for Business Server e Office Communications Server 2007 R2.  <br/> |
|[Move-CsConferenceDirectory](/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Transfere um diretório de conferência existente de um pool para outro. Os diretórios de conferências são usados para ajudar os usuários de conferências discadas a localizar as informações da conferência.  <br/> |
|[New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Cria um novo diretório de conferência para uso na organização. Os diretórios de conferências são usados para ajudar os usuários de conferências discadas a localizar as informações da conferência.  <br/> |
|[New-CsDialInConferencingAccessNumber](/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Cria um novo número de acesso de conferência discada.  <br/> |
|[New-CsDialInConferencingConfiguration](/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Cria uma nova coleção de definições de configuração de conferências discadas. Essas configurações determinam como o Skype for Business Server responde quando os usuários ins juntam ou saem de uma conferência discagem. Mais especificamente, retornam-se informações sobre a exigência feita aos participantes de registrarem ou não o seu nome ao entrar em uma conferência e como (ou se) o sistema anunciará que alguém entrou na chamada ou a abandonou.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Cria uma uma nova coleção de configurações de sinalização DTMF (multifrequência de tom dual) usada para conferência discada.  <br/> |
|[New-CsDialPlan](/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Cria um novo plano de discagem.  <br/> |
|[Remove-CsConferenceDirectory](/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Remove um diretório de conferência existente. Os diretórios de conferências são usados para ajudar os usuários de conferências discadas a localizar as informações da conferência.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Remove um número de acesso de conferência discada.  <br/> |
|[Remove-CsDialInConferencingConfiguration](/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Remove uma ou mais coleções das definições de configuração da conferência discada. Essas configurações determinam como o Skype for Business Server responde quando os usuários ins juntam ou saem de uma conferência discagem.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Remove uma coleção existente de configurações de sinalização DTMF (dual-tone multi-frequency) usadas para conferência discada.  <br/> |
|[Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Modifica os valores da propriedade de um número de acesso de conferência discada existente. A conferência discada oferece uma maneira de usuários ingressarem na porção de áudio de uma conferência utilizando telefones e celulares "comuns e outros dispositivos na PSTN (rede telefônica pública comutada).  <br/> |
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
   
**Outras configurações de conferência**

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Disable-CsMeetingRoom](/powershell/module/skype/disable-csmeetingroom?view=skype-ps) <br/> |Desabilita uma Skype for Business Server de reunião. Uma sala de reunião é um dispositivo de conferência designada para cenários de conferência por vídeo e colaboração em pequenas salas de conferência. Quando você desabilita um objeto de sala de reunião, remove todos os Skype for Business Server específicos do Active Directory atribuídos à conta de usuário que representa a sala de reunião. No entanto, a própria conta de usuário do Active Directory não é excluída.  <br/> |
|[Enable-CsMeetingRoom](/powershell/module/skype/enable-csmeetingroom?view=skype-ps) <br/> |Habilita uma Skype for Business Server de reunião. Para habilitar uma sala de reunião, você primeiro deve criar uma conta de usuário Active Directory que representará aquele sistema. Observe que, embora os objetos da sala de reunião sejam baseados em contas de usuário, esses objetos não serão exibidos quando você executar o cmdlet Get-CsUser.  <br/> |
|[Get-CsConferenceDisclaimer](/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) <br/> |Retorna informações sobre o aviso de isenção de responsabilidade de conferência usado em sua organização. O aviso de isenção de responsabilidade de conferência é uma mensagem que é exibida para os usuários que participam da conferência usando um hyperlink (por exemplo: usuários que colaram um link para a conferência em um navegador como o Windows Internet Explorer).  <br/> |
|[Get-CsMeetingRoom](/powershell/module/skype/get-csmeetingroom?view=skype-ps) <br/> |Retorna informações sobre todas as Skype for Business Server de reunião configuradas para uso na organização.  <br/> |
|[Move-CsMeetingRoom](/powershell/module/skype/move-csmeetingroom?view=skype-ps) <br/> |Move um Skype for Business Server de sala de reunião de um pool de Registradores para outro.  <br/> |
|[Remove-CsConferenceDisclaimer](/powershell/module/skype/remove-csconferencedisclaimer?view=skype-ps) <br/> |Limpa o texto do cabeçalho e do corpo do aviso de isenção de responsabilidade de conferência utilizado na organização. O aviso de isenção de responsabilidade de conferência é uma mensagem que é exibida para os usuários que participam da conferência usando um hyperlink (por exemplo: usuários que colaram um link para a conferência em um navegador como o Windows Internet Explorer).  <br/> |
|[Set-CsMeetingRoom](/powershell/module/skype/set-csmeetingroom?view=skype-ps) <br/> |Modifica os valores de propriedade de uma sala de Skype for Business Server de reunião existente.  <br/> |
   
**Configurações de teste**

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Test-CsASConference](/powershell/module/skype/test-csasconference?view=skype-ps) <br/> |Testa a capacidade de dois usuários participarem de uma conferência de compartilhamento de aplicativo.  <br/> |
|[Test-CsAudioConferencingProvider](/powershell/module/skype/test-csaudioconferencingprovider?view=skype-ps) <br/> |Teste para ver se um usuário pode se conectar ao seu provedor de conferência de áudio. Um provedor de conferência de áudio é uma empresa de terceiros que oferece as organizações serviços de conferência. Entre outras coisas, os provedores de conferência de áudio permite os usuários longe do local e não conectados à rede corporativa ou pela Internet, participar na parte de áudio de uma conferência ou reunião.  <br/> |
|[Test-CsAVConference](/powershell/module/skype/test-csavconference?view=skype-ps) <br/> |Testa a capacidade de um par de usuários participar de uma conferência de áudio/vídeo (A/V).  <br/> |
|[Test-CsDataConference](/powershell/module/skype/test-csdataconference?view=skype-ps) <br/> |Verifica se um par de usuários pode ou não participar de uma conferência da Web Skype for Business Server que inclui atividades como compartilhamento ou exibição PowerPoint slides, whiteboards ou votações. O cmdlet também verifica se o serviço Skype for Business Server webconferência pode descobrir Office Web Apps Server e que um cliente pode carregar um arquivo PowerPoint para transmissão pelo Office Web Apps Server.  <br/> |
|[Test-CsDialInConferencing](/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |Verifica se um usuário pode participar de uma sessão de conferência discda.  <br/> |
|[Test-CsDialPlan](/powershell/module/skype/test-csdialplan?view=skype-ps) <br/> |Testa um número de telefone em relação a um plano de discagem (anteriormente conhecido como perfil de localidade) e retorna a regra de normalização que será aplicada ao número, bem como o número convertido depois que a regra de normalização tiver sido aplicada.  <br/> |
|[Test-CsMcxConference](/powershell/module/skype/test-csmcxconference?view=skype-ps) <br/> |Testa a capacidade de três usuários participarem de uma conferência Skype for Business Server Mobility Service. O Serviço de Mobilidade permite que os usuários de telefones celulares, como iPhones e Windows Telefones, faça coisas como trocar mensagens instantâneas e informações de presença; armazenar e recuperar a caixa postal internamente, em vez de com seu provedor sem fio; e tirar proveito de Skype for Business Server recursos como Chamada via Trabalho e conferência discagem.  <br/> **Observação:** Os clientes que usam MCX não têm suporte no Skype for Business Server 2019.|
|[Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) <br/> |Testa a capacidade de um par de usuários agendar, ingressar e conduzir uma conferência online usando a UCWA (Unified Communications Web API).  <br/> |
|[Debug-CsDataConference](/powershell/module/skype/debug-csdataconference?view=skype-ps) <br/> |Retorna informações de diagnóstico para os recursos de conferência de dados incluídos Skype for Business Server.  <br/> |
