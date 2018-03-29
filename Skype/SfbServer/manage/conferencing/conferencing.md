---
title: Gerenciar conferências no Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 825e051c-83a5-420d-a5ef-f77afa368e2e
description: 'Resumo: Saiba como gerenciar as conferências em Skype para Business Server 2015.'
ms.openlocfilehash: 2239c5aae8754e381bf6cf7b8b41aa6ef31b8033
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-conferencing-in-skype-for-business-server-2015"></a>Gerenciar conferências no Skype for Business Server 2015
 
**Resumo:** Saiba como gerenciar as conferências em Skype para Business Server 2015.
  
Este tópico descreve como gerenciar conferências. Para obter mais informações sobre como planejar e implantar a conferência, consulte [Plan para conferências no Skype para Business Server 2015](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferência no Skype para Business Server 2015](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Em Skype para Business Server, você pode gerenciar os detalhes de conferência especificando a configuração e as configurações de diretiva da seguinte maneira. Observe que os termos conferência e reunião são usados, às vezes, de forma intercambiável. Mas em geral, você pode pensar em uma reunião como uma instância específica de conferência.
  
- As **definições de política de conferência** englobam uma grande variedade de opções de agendamento e participação, desde se uma reunião pode incluir vídeo e áudio IP até o número máximo de pessoas que podem participar da reunião. Você pode usar políticas de conferência para gerenciar a segurança, a largura de banda e os aspectos legais das reuniões.
    
    Observe que políticas de conferência são aplicadas ao usuário ou site e não podem ser aplicadas a uma reunião específica. Portanto, o convite da conferência pode ser criado com antecedência algumas semanas, mas deve ser aplicada a política de conferência restritivo para Skype do organizador da reunião para a conta de negócios imediatamente antes de inicia a conferência. 
    
    Se uma conta dedicada for usada para a função Organizador da Reunião, a política de conferência poderá permanecer atribuída a essa conta. Se o organizador da reunião usa um Skype geral para a conta de negócios, a política deve ser removida após o término da conferência.
    
- As **definições de configuração de reunião** ditam os tipos de reuniões que os usuários podem criar, além de controlar como (ou até mesmo se) usuários anônimos e usuários de conferência discada podem participar dessas reuniões. Observe que essas configurações afetam apenas as reuniões agendadas. As configurações de reunião são aplicadas por pool, por site ou globalmente.
    
- **Definições de configuração de conferência** determinam coisas como o tamanho máximo permitido para o conteúdo das reuniões e folhetos; quantidade máxima de largura de banda para o serviço de conferência de compartilhamento de aplicativo; limites de armazenamento e períodos de expiração; as URLs internas e externas downloads do cliente com suporte; ponteiros para URLs internas e externas, onde os usuários podem obter ajuda de conferência e recursos; e as portas usadas para compartilhamento de aplicativos, áudio do cliente, transferências de arquivos e tráfego de mídia.
    
    Essas configurações permitem que você gerencie os servidores reais. Essas configurações só podem ser definidas por meio Skype do Shell de gerenciamento do servidor de negócios. 
    
- As **configurações de acesso discado** permitem definir as informações sobre se e como os usuários discam de um telefone. Você especifica algumas das informações de acesso discado, como número de acesso, na guia Conferências do Painel de Controle e algumas informações de discagem, como plano de discagem, política de voz, rota e uso de PSTN -- na guia Roteamento de Voz do Painel de Controle.
    
- As **configurações de política de PIN** permitem que você denomine e defina o PIN que os participantes utilizam para acesso discado.
    
## <a name="manage-conferencing-by-using-skype-for-business-server-control-panel-or-by-using-skype-for-business-server-management-shell"></a>Gerenciar as conferências usando Skype para o painel de controle do Business Server ou usando o Skype do Shell de gerenciamento do servidor de negócios

Você pode gerenciar a maioria das políticas de conferência e definições de configuração usando Skype para o painel de controle do Business Server ou usando o Skype do Shell de gerenciamento do servidor de negócios. Algumas configurações estão disponíveis somente por meio do Skype do Shell de gerenciamento do servidor de negócios.
  
- Para gerenciar configurações de política de conferência:
    
  - No Painel de Controle, selecione **Conferência | Política de Conferência**.
    
  - No PowerShell, procure os cmdlets **-CsConferencingPolicy**.
    
- Para gerenciar configurações de reunião:
    
  - No Painel de Controle, selecione **Conferência | Configuração de reunião**.
    
  - No Skype do Shell de gerenciamento do servidor de negócios, de pesquisa para os cmdlets **- CsMeetingConfiguration** .
    
- Para gerenciar configurações de número de acesso discado:
    
  - No Painel de Controle, selecione **Conferência | Número de acesso discado**.
    
  - No Skype do Shell de gerenciamento do servidor de negócios, de pesquisa para os cmdlets **- CsDialInConferencing** .
    
- Para gerenciar informações do acesso discado, como plano de discagem, política de voz, rota e uso PSTN: 
    
  - No Painel de Controle, selecione **Conferência | Roteamento de voz**.
    
  - No Skype do Shell de gerenciamento do servidor de negócios, pesquise os cmdlets **- CsDialPlan** e **- CsVoice** .
    
- Para gerenciar configurações de política de PIN:
    
  - No Painel de Controle, selecione **Conferência | Política de PIN**.
    
  - No Skype do Shell de gerenciamento do servidor de negócios, de pesquisa para os cmdlets **- CsPinPolicy** .
    
- Para gerenciar definições de configuração de conferência, você deve usar o Skype do Shell de gerenciamento do servidor de negócios. Procure os cmdlets **-CsConferencingConfiguration**.
    
## <a name="skype-for-business-server-management-shell-cmdlets"></a>Skype para cmdlets do Shell de gerenciamento do servidor de negócios

Você pode usar o seguinte Skype para cmdlets do Shell de gerenciamento do Business Server para gerenciar as conferências: 
  
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
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Cria uma nova coleção de configurações de reunião em escopo do site ou serviço. Observe que essas configurações só afetam reuniões programadas; eles não afetam as reuniões ad hoc criados clicando-se a opção reunir agora Skype para negócios.  <br/> |
|[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Exclui um conjunto existente de configurações de reunião.  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Modifica as definições de configuração de reunião em uso na organização.  <br/> |
   
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
|[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingconfiguration?view=skype-ps) <br/> |Recupera informações sobre como o Skype para Business Server responde quando os usuários entram ou saem de uma conferência discada.  <br/> |
|[Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Retorna informações sobre todos os números de acesso à conferência discada configurados para uso na organização.  <br/> |
|[Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Retorna as definições de sinalização DTMF (multifrequência de tom dual) utilizadas em conferências discadas. A DTMF permite que os usuários que discam para uma conferência controlem as definições da conferência (como ativar e desativar a Opção Mudo, ou bloquear e desbloquear a conferência) usando o teclado de seus telefones.  <br/> |
|[Get-CsDialInConferencingLanguageList](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencinglanguagelist?view=skype-ps) <br/> |Retorna uma lista de idiomas, inclusive idiomas regionais/minoritário, com suporte para uso com Skype para Business Server em conferências discadas. Esses idiomas são usados para retransmitir mensagens de áudio e instruções a usuários que participam de uma conferência usando um telefone.  <br/> |
|[Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps) <br/> |Retorna as informações sobre os planos de discagem utilizados na organização.  <br/> |
|[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) <br/> |Atribui um plano de discagem a um ou mais usuários ou grupos.  <br/> |
|[Import-CsLegacyConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/import-cslegacyconferencedirectory?view=skype-ps) <br/> |Importa diretórios de conferência do Microsoft Office Communications Server 2007 R2 para Skype para Business Server. Isso ajuda a fornecer interoperabilidade entre Skype para Business Server e o Office Communications Server 2007 R2.  <br/> |
|[Move-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/move-csconferencedirectory?view=skype-ps) <br/> |Transfere um diretório de conferência existente de um pool para outro. Os diretórios de conferências são usados para ajudar os usuários de conferências discadas a localizar as informações da conferência.  <br/> |
|[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps) <br/> |Cria um novo diretório de conferência para uso na organização. Os diretórios de conferências são usados para ajudar os usuários de conferências discadas a localizar as informações da conferência.  <br/> |
|[New-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Cria um novo número de acesso de conferência discada.  <br/> |
|[New-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingconfiguration?view=skype-ps) <br/> |Cria uma nova coleção de definições de configuração de conferências discadas. Essas configurações determinam como o Skype para Business Server responde quando os usuários entram ou saem de uma conferência discada. Mais especificamente, são retornadas informações sobre a exigência feita aos participantes de registrarem ou não o seu nome ao entrar em uma conferência e como (ou se) o sistema anunciará que alguém entrou na chamada ou a abandonou.  <br/> |
|[New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Cria uma uma nova coleção de configurações de sinalização DTMF (multifrequência de tom dual) usada para conferência discada.  <br/> |
|[New-CsDialPlan.](https://docs.microsoft.com/powershell/module/skype/new-csdialplan?view=skype-ps) <br/> |Cria um novo plano de discagem.  <br/> |
|[Remove-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedirectory?view=skype-ps) <br/> |Remove um diretório de conferência existente. Os diretórios de conferência são usados para ajudar os usuários de conferências discadas a localizar informações da conferência.  <br/> |
|[Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Remove um número de acesso de conferência discada existente.  <br/> |
|[Remove-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingconfiguration?view=skype-ps) <br/> |Remove uma ou mais coleções das definições de configuração da conferência discada. Essas configurações determinam como o Skype para Business Server responde quando os usuários entram ou saem de uma conferência discada.  <br/> |
|[Remove-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Remove uma coleção existente de definições de sinalização DTMF (multifrequência de tom dual) usada para conferência discada.  <br/> |
|[Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) <br/> |Modifica os valores da propriedade de um número de acesso de conferência discada existente. A conferência discada oferece uma maneira de usuários ingressarem na porção de áudio de uma conferência utilizando telefones e celulares "comuns e outros dispositivos na PSTN (rede telefônica pública comutada).  <br/> |
|[Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) <br/> |Modifica as definições que determinam como o Skype para Business Server responde quando os usuários entram ou saem de uma conferência discada.  <br/> |
|[Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps) <br/> |Modifica as definições de sinalização DTMF (multifrequência de tom dual) utilizadas em conferências discadas.  <br/> |
|[Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps) <br/> |Modifica um plano de discagem existente.  <br/> |
   
**Configurações de diretiva PIN**

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) <br/> |Retorna informações sobre as diretivas de PIN do cliente configuradas para uso na organização. Autenticação de PIN permite que os usuários acessem Skype para Business Server, fornecendo um PIN em vez de um nome de usuário e senha.  <br/> |
|[Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps) <br/> |Atribui um número de identificação pessoal (PIN) de cliente a um usuário ou grupo de usuários.  <br/> |
|[New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps) <br/> |Cria uma nova política de número de identificação pessoal (PIN) do cliente.  <br/> |
|[Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) <br/> |Remove a diretiva de PIN especificada.  <br/> |
|[Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps) <br/> |Modifica uma ou várias políticas existentes de números de identificação pessoal (PINs) de cliente.  <br/> |
   
**Outras configurações de conferência**

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/disable-csmeetingroom?view=skype-ps) <br/> |Desabilita um Skype para sala de reunião Business Server. Uma sala de reunião é um dispositivo de conferência para resolver cenários de colaboração e conferência de vídeo em pequenas salas de conferência. Quando você desabilitar uma sala de reunião é remover todos o Skype dos atributos do Active Directory de negócios específicas de servidor atribuída à conta de usuário que representa a sala de reunião do objeto. No entanto, a própria conta de usuário do Active Directory não é excluída.  <br/> |
|[Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/enable-csmeetingroom?view=skype-ps) <br/> |Permite que um Skype para sala de reunião Business Server. Para habilitar uma sala de reunião, você primeiro deve criar uma conta de usuário Active Directory que representará aquele sistema. Observe que, embora os objetos da sala de reunião sejam baseados em contas de usuário, esses objetos não serão exibidos quando você executar o cmdlet Get-CsUser.  <br/> |
|[Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) <br/> |Retorna informações sobre o aviso de isenção de responsabilidade de conferência usado na organização. O aviso de isenção de responsabilidade de conferência é uma mensagem que é exibida aos usuários que ingressam na conferência usando um hyperlink (por exemplo: usuários que colam o link para a conferência em um navegador, como o Windows Internet Explorer).  <br/> |
|[Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/get-csmeetingroom?view=skype-ps) <br/> |Retorna informações sobre todos o Skype para Business Server configuradas para uso na organização de salas de reunião.  <br/> |
|[Move-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/move-csmeetingroom?view=skype-ps) <br/> |Move um Skype para Business Server reunião o objeto de sala de um pool de registrador para outra.  <br/> |
|[Remove-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/remove-csconferencedisclaimer?view=skype-ps) <br/> |Limpa o texto do cabeçalho e do corpo do aviso de isenção de responsabilidade de conferência utilizado na organização. O aviso de isenção de responsabilidade de conferência é uma mensagem que é exibida para os usuários que participam da conferência usando um hyperlink (por exemplo: usuários que colaram um link para a conferência em um navegador como o Windows Internet Explorer).  <br/> |
|[Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/set-csmeetingroom?view=skype-ps) <br/> |Modifica os valores de propriedade de um existente Skype para sala de reunião Business Server.  <br/> |
   
**Configurações de testes**

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|[Test-CsASConference](https://docs.microsoft.com/powershell/module/skype/test-csasconference?view=skype-ps) <br/> |Testa a capacidade de dois usuários de participar de uma conferência de compartilhamento de aplicativo.  <br/> |
|[Test-CsAudioConferencingProvider](https://docs.microsoft.com/powershell/module/skype/test-csaudioconferencingprovider?view=skype-ps) <br/> |Testa para verificar se um usuário pode se conectar ao seu provedor de conferência de áudio. Um provedor de conferência de áudio é uma empresa de terceiros que oferece serviços de conferência às organizações. Entre outras coisas, os provedores de conferência de áudio permitem que usuários que estiverem longe do local e não conectados à rede corporativa ou pela Internet participem do áudio de uma conferência ou reunião.  <br/> |
|[Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/test-csavconference?view=skype-ps) <br/> |Testa a capacidade de um par de usuários participar de uma conferência de áudio/vídeo (A/V).  <br/> |
|[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/test-csdataconference?view=skype-ps) <br/> |Verifica se é ou não um par de usuários pode participar de uma Skype para Webconferência Business Server que inclui atividades como compartilhamento ou exibição de slides do PowerPoint, quadros de comunicações ou votações. O cmdlet também verifica se o Skype para serviço de webconferência Business Server pode descobrir os Office Web Apps Server e que um cliente pode carregar um arquivo do PowerPoint para transmissão pelo Office Web Apps Server.  <br/> |
|[Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps) <br/> |Verifica se um usuário pode participar de uma sessão de conferência discada.  <br/> |
|[Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/test-csdialplan?view=skype-ps) <br/> |Testa um número de telefone em relação a um plano de discagem (anteriormente conhecido como perfil de localidade) e retorna a regra de normalização que será aplicada ao número, bem como o número convertido depois que a regra de normalização tiver sido aplicada.  <br/> |
|[Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/test-csmcxconference?view=skype-ps) <br/> |Testa a capacidade de três usuários participem de uma Skype para conferência de serviço de mobilidade do Business Server. O serviço de mobilidade permite que os usuários de celulares como iPhones e Windows Phones fazer coisas como trocar mensagens instantâneas e informações de presença; armazenar e recuperar caixa postal internamente, em vez de com seu provedor sem fio; e aproveitar Skype para recursos de Business Server, como chamada via trabalho e conferências de discagem.  <br/> |
|[Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) <br/> |Testa a capacidade de um par de usuários para participar, programar e conduzir uma conferência online usando a Unified Communications Web API (UCWA).  <br/> |
|[Debug-CsDataConference](https://docs.microsoft.com/powershell/module/skype/debug-csdataconference?view=skype-ps) <br/> |Retorna informações de diagnóstico para os recursos de conferência de dados incluídas no Skype para Business Server.  <br/> |
   

