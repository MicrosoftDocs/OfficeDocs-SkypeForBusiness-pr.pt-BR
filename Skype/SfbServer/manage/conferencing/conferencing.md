---
title: Gerenciar conferências no Skype for Business Server
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
ms.assetid: 825e051c-83a5-420d-a5ef-f77afa368e2e
description: 'Resumo: saiba como gerenciar a conferência no Skype for Business Server.'
ms.openlocfilehash: 321241be405789e5a8b0f9440fddd09f738911ac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818622"
---
# <a name="manage-conferencing-in-skype-for-business-server"></a>Gerenciar conferências no Skype for Business Server
 
**Resumo:** Saiba como gerenciar conferências no Skype for Business Server.
  
Este tópico descreve como gerenciar conferências. Para obter mais informações sobre como planejar e implantar a conferência, consulte [planejar conferências no Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) e [implantar conferências no Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
No Skype for Business Server, você gerencia os detalhes da conferência especificando as configurações de política e configuração da seguinte maneira. Observe que os termos conferência e reunião são usados, às vezes, de forma intercambiável. Mas em geral, você pode pensar em uma reunião como uma instância específica de conferência.
  
- As **definições de política de conferência** englobam uma grande variedade de opções de agendamento e participação, desde se uma reunião pode incluir vídeo e áudio IP até o número máximo de pessoas que podem participar da reunião. Você pode usar políticas de conferência para gerenciar a segurança, a largura de banda e os aspectos legais das reuniões.
    
    Observe que políticas de conferência são aplicadas ao usuário ou site e não podem ser aplicadas a uma reunião específica. Portanto, o convite da reunião para a conferência pode ser criado algumas semanas antecipadamente, mas a política de conferência restritiva deve ser aplicada à conta do Skype for Business do organizador da reunião logo antes da conferência começar. 
    
    Se uma conta dedicada for usada para a função Organizador da Reunião, a política de conferência poderá permanecer atribuída a essa conta. Se o organizador da reunião usa uma conta geral do Skype for Business, a política deve ser removida após a conclusão da conferência.
    
- As **definições de configuração de reunião** ditam os tipos de reuniões que os usuários podem criar, além de controlar como (ou até mesmo se) usuários anônimos e usuários de conferência discada podem participar dessas reuniões. Observe que essas configurações afetam apenas as reuniões agendadas. As configurações de reunião são aplicadas por pool, por site ou globalmente.
    
- **As configurações de conferência** determinam itens como o tamanho máximo permitido para o conteúdo da reunião e folhetos; quantidade máxima de largura de banda para o serviço de conferência de compartilhamento de aplicativos; limites de armazenamento e períodos de expiração; as URLs dos downloads internos e externos do cliente compatível; ponteiros para URLs internas e externas em que os usuários podem obter ajuda e recursos de conferência; e as portas usadas para compartilhamento de aplicativos, áudio do cliente, transferências de arquivos e tráfego de mídia.
    
    Essas configurações permitem que você gerencie os servidores reais. Essas configurações só podem ser definidas usando o Shell de gerenciamento do Skype for Business Server. 
    
- As **configurações de acesso discado** permitem definir as informações sobre se e como os usuários discam de um telefone. Você especifica algumas das informações de acesso discado, como número de acesso, na guia Conferências do Painel de Controle e algumas informações de discagem, como plano de discagem, política de voz, rota e uso de PSTN -- na guia Roteamento de Voz do Painel de Controle.
    
- As **configurações de política de PIN** permitem que você denomine e defina o PIN que os participantes utilizam para acesso discado.
    
## <a name="manage-conferencing-by-using-skype-for-business-server-control-panel-or-by-using-skype-for-business-server-management-shell"></a>Gerenciar conferências usando o painel de controle do Skype for Business Server ou usando o Shell de gerenciamento do Skype for Business Server

Você pode gerenciar a maioria das políticas de conferência e as configurações de configuração usando o painel de controle do Skype for Business Server ou usando o Shell de gerenciamento do Skype for Business Server. Algumas configurações estão disponíveis apenas usando o Shell de gerenciamento do Skype for Business Server.
  
- Para gerenciar configurações de política de conferência:
    
  - No Painel de Controle, selecione **Conferência | Política de Conferência**.
    
  - No PowerShell, procure os cmdlets **-CsConferencingPolicy**.
    
- Para gerenciar configurações de reunião:
    
  - No Painel de Controle, selecione **Conferência | Configuração de reunião**.
    
  - No Shell de gerenciamento do Skype for Business Server, procure cmdlets **-CsMeetingConfiguration** .
    
- Para gerenciar configurações de número de acesso discado:
    
  - No Painel de Controle, selecione **Conferência | Número de acesso discado**.
    
  - No Shell de gerenciamento do Skype for Business Server, procure cmdlets **-CsDialInConferencing** .
    
- Para gerenciar informações do acesso discado, como plano de discagem, política de voz, rota e uso PSTN: 
    
  - No Painel de Controle, selecione **Conferência | Roteamento de voz**.
    
  - No Shell de gerenciamento do Skype for Business Server, procure os cmdlets **-CsDialPlan** e **-CsVoice** .
    
- Para gerenciar configurações de política de PIN:
    
  - No Painel de Controle, selecione **Conferência | Política de PIN**.
    
  - No Shell de gerenciamento do Skype for Business Server, procure cmdlets **-CsPinPolicy** .
    
- Para gerenciar as configurações de configuração de conferência, você deve usar o Shell de gerenciamento do Skype for Business Server. Procure os cmdlets **-CsConferencingConfiguration**.
    
## <a name="skype-for-business-server-management-shell-cmdlets"></a>Cmdlets do Shell de gerenciamento do Skype for Business Server

Você pode usar os seguintes cmdlets do Shell de gerenciamento do Skype for Business Server para gerenciar a conferência: 
  
**Configurações de política de conferência**

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Retorna informações sobre as diretivas de conferência que tenham sido configuradas para uso na organização. As diretivas de conferência determinam os recursos e capacidades que podem ser usados em uma conferência; isso inclui tudo, desde o fato de a conferência poder ou não incluir áudio e vídeo IP até o número máximo de pessoas que podem participar de uma reunião.  <br/> |
|[Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Atribui uma diretiva de conferência em escopo por usuário.  <br/> |
|[New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Cria uma nova política de conferência para uso na organização.  <br/> |
|[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Remove a diretiva de conferência especificada.  <br/> |
|[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Modifica uma diretiva de conferência existente.  <br/> |
   
**Definições de configuração de reunião**

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Retorna informações sobre as configurações de reunião atualmente em uso na sua organização. As configurações de reunião ajudam a ditar os tipos de reuniões que os usuários podem criar, além de controlar como (ou se) usuários anônimos e usuários de conferência discada podem ingressar nessas reuniões.  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Cria uma nova coleção de configurações de reunião em escopo do site ou serviço. Observe que essas configurações só afetam reuniões agendadas; Elas não afetam reuniões ad hoc criadas quando você clica na opção reunir agora no Skype for Business.  <br/> |
|[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Exclui um conjunto existente das configurações de reunião.  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Modifica as configurações de reunião atualmente em uso na sua organização.  <br/> |
   
**Definições de configuração de conferência**

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Retorna informações sobre as definições de configuração de conferências da organização. As definições de conferências determinam aspectos como o tamanho máximo permitido do conteúdo e dos folhetos da conferência, o período de cortesia do conteúdo (ou seja, o tempo que o conteúdo será armazenado antes de ser excluído) e os URLs dos downloads internos e externos do cliente suportado.  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Cria uma nova coleção definições de configuração de conferências.  <br/> |
|[Remove-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Remove o conjunto especificado de definições de configuração de conferências.  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Modifica um conjunto existente de definições de configuração de conferências.  <br/> |
   
**Definições de configuração de discagem**

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Get-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/get-csconferencedirectory?view=skype-ps) <br/> |Retorna informações sobre os diretórios de conferências configurados para uso em sua organização. Os diretórios de conferência são usados para ajudar usuários de conferência discada a localizar informações de conferência.  <br/> |
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Recupera informações sobre como o Skype for Business Server responde quando os usuários unem ou deixam uma conferência discada.  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Retorna informações sobre todos os números de acesso à conferência discada configurados para uso na organização.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Retorna as definições de sinalização DTMF (multifrequência de tom dual) utilizadas em conferências discadas. A DTMF permite que os usuários que discam para uma conferência controlem as definições da conferência (como ativar e desativar a Opção Mudo, ou bloquear e desbloquear a conferência) usando o teclado de seus telefones.  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Retorna uma lista de idiomas, incluindo idiomas regionais/minoritários, com suporte para uso com conferências discada do Skype for Business Server. Esses idiomas são usados para retransmitir mensagens de áudio e instruções a usuários que participam de uma conferência usando um telefone.  <br/> |
|[Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Retorna as informações sobre os planos de discagem utilizados na organização.  <br/> |
|[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Atribui um plano de discagem a um ou mais usuários ou grupos.  <br/> |
|[Import-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Importa diretórios de conferência do Microsoft Office Communications Server 2007 R2 para o Skype for Business Server. Isso ajuda a oferecer interoperabilidade entre o Skype for Business Server e o Office Communications Server 2007 R2.  <br/> |
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Transfere um diretório de conferência existente de um pool para outro. Os diretórios de conferências são usados para ajudar os usuários de conferências discadas a localizar as informações da conferência.  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Cria um novo diretório de conferência para uso na organização. Os diretórios de conferências são usados para ajudar os usuários de conferências discadas a localizar as informações da conferência.  <br/> |
|[New-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Cria um novo número de acesso de conferência discada.  <br/> |
|[New-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Cria uma nova coleção de definições de configuração de conferências discadas. Essas configurações determinam como o Skype for Business Server responde quando os usuários unem ou deixam uma conferência discada. Mais especificamente, são retornadas informações sobre a exigência feita aos participantes de registrarem ou não o seu nome ao entrar em uma conferência e como (ou se) o sistema anunciará que alguém entrou na chamada ou a abandonou.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Cria uma uma nova coleção de configurações de sinalização DTMF (multifrequência de tom dual) usada para conferência discada.  <br/> |
|[New-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Cria um novo plano de discagem.  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Remove um diretório de conferência existente. Os diretórios de conferência são usados para ajudar os usuários de conferências discadas a localizar informações da conferência.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Remove um número de acesso de conferência discada existente.  <br/> |
|[Remove-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Remove uma ou mais coleções das definições de configuração da conferência discada. Essas configurações determinam como o Skype for Business Server responde quando os usuários unem ou deixam uma conferência discada.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Remove uma coleção existente de definições de sinalização DTMF (multifrequência de tom dual) usada para conferência discada.  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Modifica os valores da propriedade de um número de acesso de conferência discada existente. A conferência discada oferece uma maneira de usuários ingressarem na porção de áudio de uma conferência utilizando telefones e celulares "comuns e outros dispositivos na PSTN (rede telefônica pública comutada).  <br/> |
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
   
**Outras configurações de conferência**

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/disable-csmeetingroom?view=skype-ps) <br/> |Desabilita uma sala de reunião do Skype for Business Server. Uma sala de reunião é um dispositivo de conferência projetado para resolver cenários de colaboração e conferência de vídeo em pequenas salas de conferência. Ao desabilitar um objeto de sala de reunião, você remove todos os atributos do Active Directory específicos do Skype for Business Server atribuídos à conta de usuário que representa a sala de reunião. No entanto, a própria conta de usuário do Active Directory não é excluída.  <br/> |
|[Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/enable-csmeetingroom?view=skype-ps) <br/> |Habilita uma sala de reunião do Skype for Business Server. Para habilitar uma sala de reunião, você primeiro deve criar uma conta de usuário Active Directory que representará aquele sistema. Observe que, embora os objetos da sala de reunião sejam baseados em contas de usuário, esses objetos não serão exibidos quando você executar o cmdlet Get-CsUser.  <br/> |
|[Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) <br/> |Retorna informações sobre o aviso de isenção de responsabilidade de conferência usado na organização. O aviso de isenção de responsabilidade de conferência é uma mensagem que é exibida aos usuários que ingressam na conferência usando um hyperlink (por exemplo: usuários que colam o link para a conferência em um navegador, como o Windows Internet Explorer).  <br/> |
|[Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/get-csmeetingroom?view=skype-ps) <br/> |Retorna informações sobre todas as salas de reunião do Skype for Business Server configuradas para uso na organização.  <br/> |
|[Move-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/move-csmeetingroom?view=skype-ps) <br/> |Move um objeto de sala de reunião do Skype for Business Server de um pool de registradores para outro.  <br/> |
|[Remove-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedisclaimer?view=skype-ps) <br/> |Limpa o texto do cabeçalho e do corpo do aviso de isenção de responsabilidade de conferência utilizado na organização. O aviso de isenção de responsabilidade de conferência é uma mensagem que é exibida para os usuários que participam da conferência usando um hyperlink (por exemplo: usuários que colaram um link para a conferência em um navegador como o Windows Internet Explorer).  <br/> |
|[Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/set-csmeetingroom?view=skype-ps) <br/> |Modifica os valores de propriedade de uma sala de reunião do Skype for Business Server existente.  <br/> |
   
**Configurações de teste**

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Test-CsASConference](https://docs.microsoft.com/powershell/module/skype/test-csasconference?view=skype-ps) <br/> |Testa a capacidade de dois usuários de participar de uma conferência de compartilhamento de aplicativo.  <br/> |
|[Test-CsAudioConferencingProvider](https://docs.microsoft.com/powershell/module/skype/test-csaudioconferencingprovider?view=skype-ps) <br/> |Testa para verificar se um usuário pode se conectar ao seu provedor de conferência de áudio. Um provedor de conferência de áudio é uma empresa de terceiros que oferece serviços de conferência às organizações. Entre outras coisas, os provedores de conferência de áudio permitem que usuários que estiverem longe do local e não conectados à rede corporativa ou pela Internet participem do áudio de uma conferência ou reunião.  <br/> |
|[Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/test-csavconference?view=skype-ps) <br/> |Testa a capacidade de um par de usuários participar de uma conferência de áudio/vídeo (A/V).  <br/> |
|[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/test-csdataconference?view=skype-ps) <br/> |Verifica se um par de usuários pode participar de uma conferência da Web do Skype for Business Server que inclui atividades como o compartilhamento ou a exibição de slides do PowerPoint, quadros de comunicações ou votação. O cmdlet também verifica se o serviço de Webconferência do Skype for Business Server pode descobrir o Office Web Apps Server e se um cliente pode carregar um arquivo do PowerPoint para transmissão pelo servidor dos Office Web Apps.  <br/> |
|[Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |Verifica se um usuário pode participar de uma sessão de conferência discada.  <br/> |
|[Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/test-csdialplan?view=skype-ps) <br/> |Testa um número de telefone em relação a um plano de discagem (anteriormente conhecido como perfil de localidade) e retorna a regra de normalização que será aplicada ao número, bem como o número convertido depois que a regra de normalização tiver sido aplicada.  <br/> |
|[Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/test-csmcxconference?view=skype-ps) <br/> |Testa a capacidade de três usuários participarem de uma conferência do serviço de mobilidade do Skype for Business Server. O serviço de mobilidade permite que os usuários de telefones celulares, como iPhones e telefones Windows, façam coisas como mensagens instantâneas e informações de presença do Exchange; armazene e recupere a caixa postal internamente em vez de usar o seu provedor sem fio; e aproveite os recursos do Skype for Business Server, como a chamada via Conferência de trabalho e discada.  <br/> **Observação:** Os clientes que usam o MCX não são compatíveis com o Skype for Business Server 2019.|
|[Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) <br/> |Testa a capacidade de um par de usuários para participar, programar e conduzir uma conferência online usando a Unified Communications Web API (UCWA).  <br/> |
|[Debug-CsDataConference](https://docs.microsoft.com/powershell/module/skype/debug-csdataconference?view=skype-ps) <br/> |Retorna informações de diagnóstico dos recursos de conferência de dados incluídos no Skype for Business Server.  <br/> |
   

