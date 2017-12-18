---
title: "Solução de conferência de áudio e problemas conhecidos"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
ms.assetid: 72979911-5319-4de2-a275-4dd9a0f44fe6

description: "Get a list of known isses when using Microsoft as their dial-in conference provider, status, and some work arounds. "
---

# Solução de conferência de áudio e problemas conhecidos

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade.  
  
 **Este artigo é para o Skype para usuários de negócios e Teams da Microsoft usando o Microsoft como seu provedor de audioconferência. Ele não se aplica aos clientes que estão usando um provedor de terceiros audioconferência (ACP).**
  
## Problemas conhecidos e solução de problemas

Conferência de áudio que usa o Microsoft como provedor de audioconferência tem problemas atuais que estão sendo controladas e ativamente investigação e serão potencialmente resolvidos quando o recurso for atualizado no futuro versões do Office 365.
  
Por agora, use este documento como uma referência para solucionar possíveis problemas com a obtenção de conferência de áudio, configurar e trabalhar para as pessoas que usam o Skype para aplicativos de negócios ou Teams da Microsoft em sua organização.
  
### Aplicativo de equipes da Microsoft

|**Problema**|**Comportamento/sintomas**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Os chamadores PSTN com o mesmo "número de" são mostrados como o mesmo usuário na lista de participação da reunião.  <br/> |Quando vários chamadores de PSTN ingressar em uma reunião e suas identificações de chamador são mascaradas como um único número, ele aparecerá como um chamador único na lista da reunião.  <br/> |Não há solução alternativa.  <br/> |25/9/2017  <br/> |
|Painel de informações de reunião não estiver aparecendo intermitentemente.  <br/> |Painel de informações da reunião pode não aparecer no cliente de equipes quando os usuários tentam pesquisar para números de telefone de ponte de conferência ou ID da conferência.  <br/> |Examine os detalhes da reunião ou o calendário do Outlook para exibir números de telefone de ponte de conferência ou ID da conferência.  <br/> |25/9/2017  <br/> |
|Convites de reunião de suplemento do Outlook mostram caracteres de lixo em coordenadas PSTN para localidades fora dos EUA.  <br/> |Ao agendar reuniões particulares usando o suplemento do Outlook para Microsoft Teams em um computador com localidades fora dos EUA, coordenadas PSTN podem conter caracteres de lixo.  <br/> |Não há solução alternativa.  <br/> |25/9/2017  <br/> |
|Discar precisa usar 5 dígitos ou mais.  <br/> |Os usuários tentando discar de uma reunião precisam digitar em 5 ou mais dígitos, apesar de regra de normalização de plano de discagem está disponível para normalizar discagem dígito curto para e. 164.  <br/> |Discar digitando o número DID completo ou o formato de número local em vez de número de ramal interno.  <br/> |25/9/2017  <br/> |
|Discar controle não estiver aparecendo intermitentemente.  <br/> |Controle de discagem pode não estar visível do painel de informações de reunião.  <br/> |Não há solução alternativa.  <br/> |25/9/2017  <br/> |
|ID de conferência estático não tem suportada para reuniões de Teams da Microsoft.  <br/> |Se o administrador substitui a configuração padrão de ID de conferência dinâmicos a ID de conferência estático, essa configuração não terá efeito para reuniões de Teams da Microsoft. Consulte [Usando IDs de dinâmico de conferência de áudio em sua organização](using-audio-conferencing-dynamic-ids-in-your-organization.md).  <br/> |Não há solução alternativa.  <br/> |25/9/2017  <br/> |
   
### Skype for Business app

|**Problema**|**Comportamento/sintomas**|**Solução alternativa conhecida**|**Data da descoberta**|
|:-----|:-----|:-----|:-----|
|Notificações de entrada e saída estiver ativada quando inicia uma reunião, mas eles estão desativados logo após a reunião comece.  <br/> |Por padrão, as notificações de entrada e saída estão desabilitadas para reuniões onde os participantes ingressar de ambas as Skype para os aplicativos de negócios e quando eles discam. Você pode habilitar os anúncios nas **Opções de reunião do Skype** o Skype para o aplicativo de negócios. Para uma reunião em que todos os participantes discar e ingressar em uma reunião, as notificações de entrada e saída são ativadas por padrão, como a lista de participantes não está disponível para todos os participantes. Quando uma reunião foi iniciado com apenas os participantes da chamada, a entrada e saída notificações serão ativadas, mas quando um participante junções usando um Skype aplicativo for Business, as notificações serão desativados. Quando desativada, as notificações podem ser habilitadas novamente usando **Opções de reunião do Skype** no Skype para o aplicativo de negócios. <br/> |Não há solução alternativa.  <br/> |30/8/2017  <br/> |
|Se um usuário está provisionado na primeira vez por sendo atribuído uma licença E5, talvez seja possível para o email de boas-vindas de conferência de áudio não ser entregue para o usuário se a caixa de correio não está habilitada.  <br/> |Se isso acontecer, você sempre pode reenviar as informações de conferência de áudio do usuário usando **conferências de áudio** do Skype para o Centro de administração de negócios ou usando o PowerShell. Consulte[Ativar ou desativar o envio de emails quando alterar configurações de conferência de áudio](enable-or-disable-sending-emails-when-audio-conferencing-settings-change.md).  <br/> > [!NOTE]> Para reenviar o PIN de conferência de áudio para o usuário, o PIN deve ser redefinido. Isso também pode ser feito usando **a conferência de áudio** no Skype para o Centro de administração de negócios ou usando o PowerShell.          |Não há solução alternativa.  <br/> |30/8/2017  <br/> |
|Chamadas de conferência de áudio podem levar até 24 horas para mostrar os relatórios de uso.  <br/> |Queremos encaminhar para fazer melhorias nesta área em atualizações futuras do serviço.  <br/> |Não há solução alternativa.  <br/> |30/8/2017  <br/> |
|Quando um chamador disca para uma ponte de conferência após a reunião foi bloqueada por um usuário Skype for Business, não há uma notificação no aplicativo de Skype for Business informando que o usuário está aguardando no lobby.  <br/> |Atualmente isso é intencional, mas levaremos em conta o feedback sobre o suporte a esse recurso em atualizações futuras do serviço.  <br/> |Não há solução alternativa.  <br/> |30/8/2017  <br/> |
   
## Tópicos Relacionados

[Configurar conferência de áudio para o Skype for Business e Teams da Microsoft](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

