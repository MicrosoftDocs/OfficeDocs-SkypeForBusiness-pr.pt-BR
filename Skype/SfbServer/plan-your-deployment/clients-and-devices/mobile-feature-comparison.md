---
title: Comparação de recursos de cliente móvel para o Skype for Business
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b2c950c9-76a5-400a-b146-9b1a22790c12
description: 'Resumo: examine o suporte do recurso para o cliente móvel enquanto planeja o Skype for Business Server.'
ms.openlocfilehash: d3d3764ee5315b4fe211b4f79ea2401b98703261
ms.sourcegitcommit: 55da03c85237b43b848e7ff9b427304c2d9e568f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2019
ms.locfileid: "34681862"
---
# <a name="mobile-client-feature-comparison-for-skype-for-business"></a>Comparação de recursos de cliente móvel para o Skype for Business
 
**Resumo:** Examine o suporte do recurso para o cliente móvel enquanto planeja o Skype for Business Server.
  
Este artigo compara os recursos e os recursos entre os clientes móveis do Skype for Business e o cliente de desktop do Skype for Business nas seguintes categorias:
  
- Conexão, notificações por push e recursos gerais
    
- Presença avançada
    
- Contatos e grupos de contato
    
- IM (sistema de mensagens instantâneas)
    
- Áudio e vídeo do Skype for Business para Skype for Business
    
- Conferência
    
- Telefonia
    
- Usuários externos
    
- Arquivamento e conformidade
    
-  Autenticação moderna
    
As tabelas a seguir listam os recursos que estão disponíveis para os usuários do Skype for Business em uma implantação local do Skype for Business Server. Os mesmos recursos também estão disponíveis para os usuários do Skype for Business Online e do Microsoft Office 365, a menos que indicado de outra forma nas notas de rodapé da tabela.
  
> [!NOTE]
> Para obter ajuda online e recursos para usuários finais, consulte [descubra o Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=528686). 
  
> [!NOTE]
> Para comparar os recursos disponíveis em outros clientes do Skype for Business, consulte [comparação de recursos do cliente de desktop do Skype for Business](desktop-feature-comparison.md). 

> [!NOTE]
> O suporte do MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype for Business Server 2019. Todos os clientes móveis atuais do Skype for Business já usam a API da Web de comunicação unificada (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdados que usam o MCX precisarão atualizar para um cliente atual.
  
## <a name="sign-in-push-notifications-and-general-features"></a>Conexão, notificações por push e recursos gerais

 
 | Recurso/funcionalidade  | Cliente de desktop do Skype for Business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|A sessão do Skype for Business permanece conectada  <br/> |& # x2714;|& # x2714; & # x2776; |& # x2714; & # x2776; |& # x2714;|
|Suporte para notificações de push  <br/> |& # x2714; & # x2778; |& # x2714;|& # x2714; & # x2779; |& # x2714; & # x2779; |
|As informações de conta de vários usuários podem ser armazenadas em cache no mesmo dispositivo  <br/> |& # x2714;||||
|Leitor de tela/voice over  <br/> |& # x2714;|& # x2714; & # x2777;           Somente em inglês  <br/> |& # x2714;|& # x2714;|
|Use um teclado externo para acessibilidade  <br/> |& # x2714;||& # x2714;|& # x2714;|
|Apoio ao Programa de Aperfeiçoamento da Experiência do Usuário  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
   
 & # x2776;  No Windows Phone, o Skype for Business se desconecta automaticamente após um período de inatividade, da seguinte maneira:
  
- Se o usuário tiver ativado as notificações por push, o Skype for Business se inscreverá após 10 dias de inatividade.
    
- Se o usuário não tiver ativado as notificações por push, o Skype for Business se inscreverá assim que o usuário sair do aplicativo.
    
Em dispositivos iOS, o Skype for Business se desconecta automaticamente após o cliente móvel não entrar em contato com o servidor por 10 dias devido à perda de conectividade de rede ou de outros problemas.
  
 & # x2777;  Somente no aplicativo.
  
 & # x2778;  As notificações ficam disponíveis quando o aplicativo é executado em segundo plano.
 
 & # x2779;  Os serviços de notificação do Google/Android/GCNS e Apple/APNS Mobile usam criptografia HTTPS/TLS para a entrega de notificações. A carga de notificação é manipulada em texto sem formatação enquanto processada pelo provedor de notificações.
 
-   O Skype for Business para Android recebe notificações simples (fornecidas via GCNS) sem dados do cliente.
-   O Skype for Business para iOS recebe notificações (fornecidas via APNS) que podem incluir dados do cliente para a chamada ou a mensagem.
 
  
## <a name="enhanced-presence-support"></a>Suporte para presença avançada


 | Recurso/capacidade  | Cliente de desktop do Skype for Business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Publicar e exibir status  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Exibir status com base nas informações de disponibilidade de calendário  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Exibir notas de status e mensagens de Ausência Temporária  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Adicionar um local personalizado  <br/> |& # x2714;||||
|Adicionar uma nota personalizada  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Publicar status com base na informação de disponibilidade do calendário   <br/> |& # x2714; & # x2776; ||||
|Definir estado de presença manual (como Ocupado, Não Incomodar e assim por diante)  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
   
 & # x2776;  Os clientes móveis do Skype for Business não atualizam a presença de um usuário com base nas informações de disponibilidade do calendário do usuário. Se um usuário do cliente móvel também estiver conectado ao cliente da área de trabalho do Skype for Business, o cliente da área de trabalho atualizará a presença do usuário com base nas informações de disponibilidade do calendário do usuário. Se o usuário estiver conectado apenas a um cliente móvel, a presença do usuário não será atualizada com base nas informações de disponibilidade do calendário.
  
## <a name="contacts-and-contact-groups-support"></a>Suporte para contatos e grupos de contatos


 | Recurso/funcionalidade  | Cliente de desktop do Skype for Business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Exibir lista de contatos  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Exibir grupos de contato  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Exibir grupos de contatos frequentes  <br/> |& # x2714;||||
|Modificar lista de contatos  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Marcar contatos para alertas de alteração de status  <br/> |& # x2714;||||
|Controlar relações de privacidade  <br/> |& # x2714;||||
|Pesquisar o catálogo de endereços corporativo  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Pesquisar lista de contatos  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Gerenciar grupos de contatos  <br/> |& # x2714;|||& # x2714;|
|Expandir grupos de distribuição  <br/> |& # x2714;|& # x2714;||& # x2714;|
|Pesquisar grupos de resposta  <br/> |& # x2714; & # x2776; |& # x2714;||& # x2714;|
|Exibir ou ocultar fotos do contato  <br/> |& # x2714;|& # x2714;|||
|Fixe um contato em sua tela inicial  <br/> ||& # x2714;|||
   
 & # x2776;  Não disponível para usuários do Skype for Business Online e/ou do Office 365.
  
## <a name="instant-messaging-support"></a>Suporte ao sistema de mensagens instantâneas


 | Recurso/capacidade  | Cliente de desktop do Skype for Business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Iniciar IM (sistema de mensagens instantâneas) com um contato  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Participar de IM com vários participantes  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Convidar outros por uma janela de conversa  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Exibir conversas atuais  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Navegar entre várias conversas de IM  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Fazer o login automaticamente de conversas de IM no Exchange  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Enviar uma conversa de IM como uma mensagem de email  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Iniciar um email para um contato  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Exibir convites de IM perdidos  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Vibrar com IM em entrada  <br/> ||& # x2714; & # x2776; |& # x2714;|& # x2714;|
   
 & # x2776;  Este dispositivo vibra toda vez que uma mensagem instantânea é recebida mesmo que a mensagem atual na conversa de mensagem instantânea seja exibida
  
## <a name="skype-for-business-to-skype-for-business-audio-and-video"></a>Áudio e vídeo do Skype for Business para Skype for Business


 | Recurso/funcionalidade  | Cliente de desktop do Skype for Business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Skype for Business para Skype for Business Voice  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Vídeo do Skype for Business-to-Skype for Business  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
   
> [!NOTE]
> Por padrão, o vídeo em um dispositivo móvel requer uma conexão Wi-Fi.  
  
## <a name="conferencing-support"></a>Suporte a conferências


 | Recurso/capacidade  | Cliente de desktop do Skype for Business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Clicar em um link no lembrete de reunião para participar de uma reunião com vídeo ou VoIP  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Participar de IM com vários participantes  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Usar a conferência discada (o servidor chama o dispositivo móvel)  <br/> |& # x2714; & # x2776; |& # x2714; & # x2776; |& # x2714; & # x2776; |& # x2714; & # x2776; |
|Usar conferência de áudio discada  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Exibir vídeo da reunião  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Exibir vídeo com vários participantes (modo de exibição de galeria)  <br/> |& # x2714;||||
|Aguardar no lobby da reunião  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Usar os controles do apresentador na reunião  <br/> |& # x2714;||||
|Acessar lista de participação da reunião detalhada para conferências de áudio  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Acessar lista de participação da reunião detalhada para conferências de IM  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Compartilhar área de trabalho ou programa  <br/> |& # x2714;||||
|Exibir o programa ou a área de trabalho compartilhada (VbSS ou RDP)  <br/> |& # x2714;|& # x2714; & # x2777; |& # x2714; & # x2777; |& # x2714; & # x2777; |
|Exibir arquivos compartilhados do PowerPoint  <br/> |& # x2714;|& # x2714; & # x2777; |& # x2714; & # x2777; & # x2778; |& # x2714; & # x2777; & # x2778;|
|Carregar e apresentar arquivos do PowerPoint  <br/> |& # x2714;||& # x2714; & # x2777; |& # x2714; & # x2777; |
|Usar ferramentas de reunião (usar quadro de comunicações, conduzir votações, compartilhar arquivos)  <br/> |& # x2714;||||
|Navegar por uma lista de suas reuniões  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Participar de uma reunião mesmo que você não tenha uma conta do Skype for Business  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Visualize mais informações sobre os participantes da reunião  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Inicie uma conversa de grupo não agendada com vários participantes diretamente de seu cliente ou dispositivo   <br/> |& # x2714;|& # x2714;|& # x2714;||
   
 & # x2776;  Para os usuários do Office 365, esse recurso requer o Enterprise Voice, que faz parte da licença e5.
  
 & # x2777;  É preciso ter uma conexão WiFi por padrão.
 
 & # x2778;  Não há suporte para a visualização de vídeo incorporado em apresentações do PowerPoint.
  
## <a name="telephony-support"></a>Suporte a telefonia


 | Recurso/funcionalidade  | Cliente de desktop do Skype for Business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|No Skype for Business, toque no ícone de chamada para chamar um contato  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Transferir uma chamada  <br/> |& # x2714;|& # x2714;|& # x2714;||
|Transferência consultiva  <br/> |& # x2714; & # x2778; ||||
|Gerenciar o encaminhamento de chamadas  <br/> |& # x2714; & # x2776; |& # x2714;|& # x2714;|& # x2714;|
|Gerenciar configurações de chamadas de equipe  <br/> |& # x2714; & # x2776; ||||
|Gerenciar representantes  <br/> |& # x2714; & # x2776; ||||
|Iniciar uma chamada para um Grupo de Resposta  <br/> |& # x2714; & # x2776; ||||
|Serviços de suporte a emergências  <br/> |& # x2714; & # x2777; ||||
|Realizar chamadas em nome de outro contato (cenário de gerente/representante)  <br/> |& # x2714; & # x2776; ||||
|Manipular as chamadas de outro contato, se configuradas como representante  <br/> |& # x2714; & # x2776; |& # x2714; & # x2776; |& # x2714; & # x2776; |& # x2714; & # x2776; |
|Use Telefonar via Trabalho   <br/> |& # x2714; & # x2776; |& # x2714;|& # x2714;||
|Acessar caixa postal  <br/> |& # x2714;|& # x2714;|& # x2714;||
|Usar o teclado no Skype for Business  <br/> |& # x2714; & # x2776; |& # x2714;|& # x2714;||
   
 & # x2776;  Disponível para usuários do Skype for Business Online e/ou Office 365 e5, e os usuários são hospedados no Skype for Business Server ou no Lync Server 2013 com Enterprise Voice habilitado.
  
 & # x2777;  Para os usuários do Skype for Business Online e/ou do Office 365, esse recurso é compatível com os parceiros da Microsoft.
  
 & # x2778;  Somente o cliente da área de trabalho do Windows.
  
## <a name="external-user-support"></a>Suporte a usuários externos


 | Recurso/capacidade  | Cliente de desktop do Skype for Business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Iniciar IM com um contato público  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Iniciar IM com um contato federado  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Conduzir chamadas de duas partes com usuários externos  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Conduzir chamadas de várias partes com usuários externos  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Use a chamada por meio do trabalho para acessar um contato federado em seu celular chamando o número do trabalho publicado & # x2776;            <br/> ||& # x2714;|& # x2714;|& # x2714;|
   
 & # x2776;  Por padrão, os usuários federados recebem a relação de privacidade de contatos externos. Para que seja possível chamar um contato federado em seu telefone celular ligando para seu número comercial publicado, o contato federado deve atribuir manualmente a você a relação de privacidade Colegas.
  
## <a name="address-book-integration"></a>Integração do catálogo de endereços


 | Recurso/funcionalidade  | Cliente de desktop do Skype for Business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Ligar para contatos do catálogo de endereços do dispositivo  <br/> ||& # x2714;|& # x2714;|& # x2714;|
|Fazer chamadas do Skype for Business para contatos diretamente do catálogo de endereços do dispositivo  <br/> ||||& # x2714;|
   
## <a name="archiving-and-compliance-support"></a>Suporte a arquivamento e conformidade


 | Recurso/capacidade  | Cliente de desktop do Skype for Business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Oferece arquivamento no lado do cliente  <br/> |& # x2714;||||
|Oferece gravação no lado do cliente  <br/> |& # x2714; & # x2776; ||||
   
 & # x2776;  Não disponível para usuários do Skype for Business Online e/ou do Office 365.
  
## <a name="modern-authentication"></a>Autenticação moderna

Essa tabela abrange os recursos que precisam de suporte à autenticação moderna.
  
A autenticação moderna também exige uma topologia descrita nas [topologias do Skype for Business com suporte à autenticação moderna](../../plan-your-deployment/modern-authentication/topologies-supported.md).
  

 | Recurso/funcionalidade  | Cliente de desktop do Skype for Business  | Windows Phone  | iOS  | Android |
|:-----|:-----|:-----|:-----|:-----|
|Autenticação moderna  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Autenticação multifator  <br/> |& # x2714;|& # x2714;|& # x2714;|& # x2714;|
|Autenticação baseada em certificado  <br/> |& # x2714; (somente dispositivo associado a um domínio)  <br/> ||& # x2714;|& # x2714;|
|Gerenciamento de aplicativos móveis (via Intune)  <br/> |||& # x2714;|& # x2714;|
   

