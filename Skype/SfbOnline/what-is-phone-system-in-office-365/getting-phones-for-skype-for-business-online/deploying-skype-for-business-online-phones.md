---
title: Implantando telefones do Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: faa17eb3-7483-4984-87f2-815d981b68ae
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: Conheça as etapas de implantação para obter o firmware correto, atualizá-lo, se necessário, atribuir licenças e definir configurações para telefones online do Skype for Business
ms.openlocfilehash: 41c6ef53469ab2de3699fd17a2d181477e143fae
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220441"
---
# <a name="deploying-skype-for-business-online-phones"></a>Implantando telefones do Skype for Business Online

Este guia de implantação ajudará você a implantar telefones IP do Skype for Business Online.
  
Em todos os tipos de empresas, ter um número de telefone permite que os usuários façam e recebam chamadas de voz, e é um requisito importante para fazer negócios. Os usuários que têm números de telefone poderão fazer chamadas de voz em todos os dispositivos Skype for Business, incluindo telefones IP, computadores e dispositivos móveis. Você pode saber mais sobre telefones IP do Skype for Business lendo [Adquirir telefones para o Skype for Business Online.](getting-phones-for-skype-for-business-online.md)
  
## <a name="deployment-steps-for-ip-phones"></a>Etapas de implantação para telefones IP

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a>Etapa 1 - Baixar os guias de administrador do fabricante e os manuais de telefone

Antes de começar, é uma boa ideia baixar os guias de administração do fabricante do telefone e os manuais do usuário do telefone.
  
- Para telefones Polycom, consulte a [Biblioteca de Documentação Poly.](https://documents.polycom.com/category/voice)
    
- Para telefones Yealink, consulte [a solução de telefones SIP Yealink Skype for Business HD.](http://www.yealink.com/products_top_2.html)
    
- Para telefones AudioCodes, consulte o Guia de Gerenciamento de [Provisionamento de Audiocodes.](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a>Etapa 2 - Certifique-se de que você está comprando ou migrando um telefone IP e firmware com suporte do Skype for Business

Um telefone e firmware compatíveis com o Skype for Business Online também é compatível com o Skype for Business Server, mas o oposto nem sempre é verdadeiro. Para garantir que você está comprando ou provisionando um telefone e firmware com suporte, consulte Obter telefones [para o Skype for Business Online.](getting-phones-for-skype-for-business-online.md)
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a>Etapa 3 : verificar se o firmware correto está instalado e atualizar o firmware, se necessário

Verifique a versão do firmware em seus telefones. Para:
  
- **Telefones Polycom VVX,** vá **para a Plataforma de** Status de Configurações  >    >  **Principal** do  >    >  **Aplicativo.**
    
- **Telefones Yealink,** vá **para Status** na tela do telefone principal.
    
- **Telefones AudioCodes,** vá para **a versão firmware** de status do dispositivo de  >  **menu** na tela  >   inicial.
    
    > [!NOTE]
    > Para obter acesso remoto aos detalhes do telefone, consulte os guias de administração do fabricante. Veja os links acima para os guias de usuário e manuais de telefone. 
  
- **Telefones Lync Phone Edition (LPE),** vá para Informações do Sistema de **Menu**  >   na tela inicial.
    
### <a name="step-4---device-update-considerations"></a>Etapa 4 - Considerações sobre a atualização do dispositivo

> [!NOTE]
> O firmware polycom antes da versão 5.5.1.X tinha um mecanismo de bloqueio de dispositivo específico do fabricante que é substituído por um "Bloqueio de Telefone" de implementação do Skype for Business. Atualizar um telefone de 5.4.X.X.X que foi protegido com "Bloqueio de Dispositivo" para 5.5.1.X com "Bloqueio de Telefone" não herdará o código PIN de "Bloqueio de Dispositivo", o que pode deixar o telefone sem segurança. Os usuários que ativaram o "Device-Lock" precisam habilitar o seguinte parâmetro perfil de dispositivo Polycom para dar aos usuários o controle do tempo de atualização (lync.deviceUpdate.popUpSK.enabled=1). 
  
As atualizações de firmware são gerenciadas pelo Serviço Skype for Business. Todo firmware de telefone certificado pelo Skype for Business é carregado para o servidor de atualização do Skype for Business e a atualização do dispositivo é habilitada em todos os telefones por padrão. Dependendo do tempo de inatividade no telefone e nos intervalos de votação, os telefones baixarão e instalarão automaticamente os builds certificados mais recentes. Você pode desabilitar as configurações de atualização do dispositivo usando o cmdlet [Set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) e definindo o parâmetro _EnableDeviceUpdate_ como `false` .
  
![Captura de tela mostrando a implantação de telefones](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
Quando um novo firmware estiver disponível e pronto para download e instalação, o telefone notificará o usuário. Os telefones Polycom notificarão o usuário e fornecerão a ele uma opção para **atualizar** ou **adiar.**
  
![Captura de tela mostrando as opções Atualizar e Adiar.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
Para um telefone Polycom, você pode atualizar o firmware no telefone selecionando **SwUpdate.**
  
![Captura de tela mostrando a opção SwUpdate](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
Você também pode optar por gerenciar atualizações de firmware usando um sistema de provisionamento de parceiros. Para o gerenciamento do sistema de provisionamento de parceiros, incluindo personalização avançada de telefone, consulte os guias de administração do fabricante.
  
> [!CAUTION]
> Certifique-se de ter uma única autoridade de atualização de dispositivo (atualização de dispositivo em banda ou um servidor de provisionamento de terceiros) para evitar loops de atualização. 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a>Etapa 5 - Configurações de configuração e infraestrutura do telefone

Você pode configurar as opções e políticas de telefone mais usadas usando cmdlets do Windows PowerShell de gerenciamento em banda do Skype for Business. Consulte [Set-CsIPPhonePolicy para obter](https://technet.microsoft.com/library/mt629497.aspx) detalhes desses parâmetros e configurações.
  
Para planejamento de infraestrutura de rede, consulte [a Estrutura de Operações do Skype.](https://www.skypeoperationsframework.com/)
  
### <a name="step-6---preparing-for-users-to-sign-in"></a>Etapa 6 - Preparar-se para que os usuários se inscrevam

Para permitir que os usuários se inscrevam com êxito em um telefone do Skype for Business Online e façam chamadas, você precisa garantir que os usuários têm as licenças corretas atribuídas. No mínimo, você precisará atribuir uma licença do Sistema de Telefonia e um Plano de Chamada. Para obter informações adicionais, você pode ver o licenciamento de complementos do [Skype for Business](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) e do Microsoft Teams e atribuir licenças do Skype for Business e do Microsoft [Teams.](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)
  
Para saber mais sobre planos de chamada, leia o Sistema de Telefonia [e os Planos de Chamada](/microsoftteams/calling-plan-landing-page)
  
- **As opções de login** disponíveis para usuários online são:
    
  - Os usuários **com telefones Polycom VVX 5XX/6XX verão:**
    
     ![Captura de tela mostrando o logon de telefones Polycom](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - Os usuários **com telefones Yealink T48G/T46G** verão:
    
     ![Captura de tela mostrando o logon de telefones Yealink.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    Para obter detalhes sobre as opções de conexão com suporte do fabricante, consulte [Obter telefones para o Skype for Business Online.](getting-phones-for-skype-for-business-online.md)
    
- **ID do Usuário** Usando o teclado virtual ou o teclado virtual do telefone (se disponível), os usuários podem usar o nome de usuário e a senha da organização para entrar no telefone. Por exemplo, eles devem usar o formato UPN como <em>amosm@contoso.com</em>  para seu nome de usuário.
    
     ![Captura de tela mostrando a tela de logon](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > A autenticação de PIN não é suportada para o Skype for Business Online para telefones IP de parceiros e LPE. 
  
- **Usando um computador** Quando o software Better Together over Ethernet (BToE) é instalado no computador do usuário e habilitado, os usuários podem entrar em seus telefones usando a janela de autenticação no aplicativo Windows Skype for Business. Consulte a Etapa 7 (opcional) - Se você tiver emparelhamento de dispositivos e [Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) para obter outras informações.
    
  > [!NOTE]
  > Os usuários devem usar o nome de usuário e a senha da organização para entrar no telefone. Por exemplo, eles devem usar o formato UPN como  <em>amosm@contoso.com</em>  para seu nome de usuário.
  
     ![Captura de tela mostrando a tela de logon](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- **Usando uma Web Sign-in:** essa é uma nova maneira de os usuários online autenticarem usando um navegador da Web padrão. Os usuários receberão um conjunto de instruções a seguir quando usarem um navegador para entrar.
    
  - Os usuários **com telefones Polycom VVX 5XX/6XX verão:**
    
     ![Captura de tela mostrando as instruções do Polycom](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - Os usuários **com telefones Yealink T48G/T46G** verão:
    
     ![Captura de tela mostrando instruções do Yealink](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    O código gerado expirará em 15 minutos. Quando expirar, o usuário terá que clicar em **Repetir** ou **OK** para gerar um novo código, dependendo do telefone.
    
  - Os usuários **com telefones Polycom VVX 5XX/6XX verão:**
    
     ![Captura de tela mostrando o código Polycom expirado](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - Os usuários **com telefones Yealink T48G/T46G** verão:
    
     ![Captura de tela mostrando o código Yealink expirado](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    Usando um navegador, navegue até o endereço exibido no telefone e insira seu nome de usuário do Skype for Business.
    
     ![Captura de tela mostrando a verificação de email](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    Insira o código mostrado no telefone.
    
     ![Captura de tela mostrando a inserção de código na tela de logon](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    Verifique se o site mostra "[Nome do fabricante do telefone] Telefone Certificado do **Skype for Business"** e clique em **Continuar.**
    
     ![Captura de tela mostrando a verificação de nome](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    Clique nas credenciais do usuário ou clique em **Usar outra conta:**
    
     ![Captura de tela mostrando as opções de credencial](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    Quando a página a seguir é exibida, é seguro fechar o navegador.
    
     ![Captura de tela mostrando a mensagem de confirmação](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > Telefones LPE para Skype for Business Online são suportados apenas por meio de conexão USB. 
  
- **Implantações com suporte** A tabela a seguir mostra os tipos de autenticação com suporte para os modelos de implantação com suporte no momento, incluindo Integração do Exchange, Autenticação moderna com MFA (Autenticação Multifa factor) e Skype for Business Online e local.
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Skype for Business** <br/> |**Exchange** <br/> |**Método Sign-In telefone** <br/> |**Acesso ao Skype for Business** <br/> |**Exchange Access com a Auth Moderna e a MFA desabilitadas** <br/> |**Exchange Access com a Auth Moderna e MFA habilitada** <br/> |
|Online  <br/> |Online  <br/> |Entrar na Web  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |
|Online  <br/> |Online  <br/> |Nome de usuário/Senha  <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|Online  <br/> |Local  <br/> |Entrar na Web  <br/> |Sim  <br/> |Não  <br/> |Não  <br/> |
|Online  <br/> |Local  <br/> |Nome de usuário/Senha  <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|Local  <br/> |Online/Local  <br/> |Autenticação de PIN  <br/> |Sim  <br/> |Não  <br/> |Não  <br/> |
|Local  <br/> |Online/Local  <br/> |Nome de usuário/Senha  <br/> |Sim  <br/> |Sim  <br/> |Não disponível  <br/> |
|Local  <br/> |Online/Local  <br/> |Entrar por computador (BTOE)  <br/> |Sim  <br/> |Sim  <br/> |Não disponível  <br/> |
   
- **Recursos de telefone** O conjunto de recursos pode variar ligeiramente com base no parceiro de telefone IP. Para obter o conjunto completo de recursos e obter mais informações sobre os recursos de cada fabricante de telefone, consulte Obter telefones [para o Skype for Business Online.](getting-phones-for-skype-for-business-online.md)
    
- **O Bloqueio de** Telefone é um recurso introduzido recentemente em telefones certificados pelo Skype for Business que é usado para proteger um telefone. Se habilitado, os usuários serão solicitados a criar um PIN após a autenticação bem-sucedida. Depois de criados, os telefones serão travados quando o tempo ocioso definido expirar, o usuário bloqueará manualmente o telefone ou sincronizará o bloqueio do telefone com o bloqueio do computador usando o Emparelhamento de Telefone. Se o PIN de bloqueio de telefone for inserido errado várias vezes, o telefone desatará o usuário ou exigirá o código de um administrador para desbloquear o telefone, mas isso variará dependendo do parceiro de telefone. O PIN do usuário deve ter entre 6 e 15 dígitos.
    
    Você pode desabilitar o Phone-Lock para sua organização (que é habilitado por padrão), alterar o tempo ocioso e escolher se os usuários podem fazer chamadas telefônicas enquanto estão bloqueados ou não usando configurações de banda. Consulte [Set-CsUCPhoneConfiguration para](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps) obter mais detalhes sobre essas configurações.
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a>Etapa 7 (opcional) - Se você tiver emparelhamento de dispositivos e Better Together over Ethernet (BToE)
<a name="BK_BTOE"> </a>

O BToE é um mecanismo de problema para telefones IP do parceiro que emparelha o telefone de um usuário com o aplicativo Windows Skype for Business. O BToE permite que os usuários:
  
- Entre no telefone IP usando o aplicativo da área de trabalho do Skype for Business (usando um computador)
    
- Sincronizar Phone-Lock com bloqueio de computador
    
- Clique para ligar
    
O BToE pode ser configurado para operar em dois modos: *Automático* (padrão) e *Manual.* Ele também pode ser habilitado (padrão)/desabilitado para usuários que usam as configurações em banda do Skype for Business. Ao operar no *modo Manual,*  os usuários terão que realizar uma etapa adicional para emparelhar o telefone com o aplicativo Windows.
  
 **Para implantar o BToE para os usuários**
  
1. Conecte o computador ao telefone usando a porta do computador.
    
     ![Captura de tela mostrando a conexão com um computador](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. Baixe e instale o software BToE mais recente do site do fabricante nos links abaixo. Para uma melhor experiência do usuário, você pode distribuir e instalar o software BToE usando uma solução de distribuição de administradores, como o Microsoft Endpoint Configuration Manager. Para saber como usar o Configuration Manager, consulte [Pacotes e programas no Configuration Manager.](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)
    
   - [Site de download de software BToE polycom](https://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [Yealink BToE Software Download](http://www.yealink.com/products_list_10.html)
    
   - [AudioCodes BToE Software Downloads](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. A configuração do servidor para BToE está definida como **Modo** Habilitado e **Automático** por padrão. Para alterar essas configurações, consulte [Set-CsIPPhonePolicy.](https://technet.microsoft.com/library/mt629497.aspx)
    
> [!NOTE]
> No momento, o BToE não tem suporte em plataformas Mac e VDI. 
  
## <a name="related-topics"></a>Tópicos relacionados
[Obtendo números de telefone de serviço do Skype for Business e do Microsoft Teams](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[Veja o que você obtém com o Sistema de Telefonia](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Disponibilidade de audioconferência e Planos de Chamadas por país e região](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
