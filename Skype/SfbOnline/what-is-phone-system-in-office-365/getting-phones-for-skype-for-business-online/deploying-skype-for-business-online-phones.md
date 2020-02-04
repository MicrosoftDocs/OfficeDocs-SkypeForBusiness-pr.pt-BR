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
description: Saiba quais são as etapas de implantação para obter o firmware correto, atualize-o, se necessário, atribua licenças e defina as configurações para telefones do Skype for Business Online
ms.openlocfilehash: 5eda8c9e21ed93b09b9033c5b70bb359894330f7
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705806"
---
# <a name="deploying-skype-for-business-online-phones"></a>Implantando telefones do Skype for Business Online

Este guia de implantação vai ajudá-lo a implantar os telefones IP do Skype for Business online.
  
Em todos os tipos de empresas, ter um número de telefone permite que os usuários façam e recebam chamadas de voz, e é uma exigência importante para fazer negócios. Os usuários que têm números de telefone poderão fazer chamadas de voz em todos os dispositivos Skype for Business, incluindo telefones IP, computadores e dispositivos móveis. Você pode saber mais sobre os telefones IP do Skype for Business lendo [obtendo telefones para o Skype for Business online](getting-phones-for-skype-for-business-online.md).
  
## <a name="deployment-steps-for-ip-phones"></a>Etapas de implantação para telefones IP

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a>Etapa 1-baixar os guias do administrador e os manuais do telefone do fabricante

Antes de começar, é uma boa ideia baixar os guias de administração do fabricante do telefone e os manuais do usuário do telefone.
  
- Para telefones Polycom, consulte o [Guia de implantação do Polycom](http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).
    
- Para telefones Yealink, consulte a [solução Yealink Skype for Business HD SIP phones](http://www.yealink.com/products_top_2.html).
    
- Para telefones AudioCodes, consulte o [Guia de gerenciamento de provisionamento do AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a>Etapa 2: Verifique se você está comprando ou migrando um telefone IP e firmware compatíveis com o Skype for Business

Um telefone e firmware compatíveis com o Skype for Business online também são compatíveis com o Skype for Business Server, mas o oposto não é sempre verdadeiro. Para verificar se você está comprando ou provisionando um número de telefone e um firmware com suporte, consulte [como obter telefones para o Skype for Business online](getting-phones-for-skype-for-business-online.md).
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a>Etapa 3-verificando se o firmware correto está instalado e atualize o firmware, se necessário

Verifique a versão do firmware em seus telefones. De
  
- **Polycom VVX**, vá para **configurações** > **status** > **** > **aplicativo** > plataforma**principal**.
    
- **Telefones Yealink**, vá até **status** na tela principal do telefone.
    
- **Telefones AudioCodes**, vá para **menu** > **** > **versão firmware** do status do dispositivo na tela inicial.
    
    > [!NOTE]
    > Para obter acesso remoto aos detalhes do telefone, consulte os guias de administração do fabricante. Veja os links acima para os guias do usuário e os manuais do telefone. 
  
- **Lync Phone Edition (LPe) phones**, vá para o **menu** > **informações do sistema** na tela iniciar.
    
### <a name="step-4---device-update-considerations"></a>Etapa 4-considerações sobre atualização de dispositivos

> [!NOTE]
> O firmware do Polycom antes do 5.5.1. X tinha um mecanismo de bloqueio de dispositivo específico do fabricante que é substituído por um "Phone-Lock" de implementação do Skype for Business. A atualização de um telefone de 5.4. X. X que foi protegido com "Device-Lock" como 5.5.1. X com "Phone-Lock" não herdará o código PIN de "Device-Lock", o que pode deixar o telefone desprotegido. Os usuários que ativaram o "Device-Lock" precisam habilitar o seguinte parâmetro de perfil de dispositivo Polycom para dar aos usuários o controle do tempo de atualização (Lync. deviceUpdate. popUpSK. Enabled = 1). 
  
As atualizações de firmware são gerenciadas pelo serviço Skype for Business. Todo firmware de telefone certificado pelo Skype for Business é carregado para o servidor de atualização do Skype for Business e a atualização do dispositivo é habilitada em todos os telefones por padrão. Dependendo do tempo de inatividade no telefone e nos intervalos de sondagem, os telefones baixarão e instalarão automaticamente as compilações certificadas mais recentes. Você pode desativar as configurações de atualização de dispositivo usando o cmdlet [set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) e definindo __ o parâmetro EnableDeviceUpdate `false`como.
  
![Captura de tela mostrando a implantação de telefones](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
Quando um novo firmware estiver disponível e estiver pronto para download e instalação, o telefone notificará o usuário. Os telefones Polycom notificarão o usuário e fornecerão uma opção para **Atualizar** ou **adiar**o usuário.
  
![Captura de tela mostrando opções de atualização e adiamento.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
Para um telefone Polycom, você pode atualizar o firmware no telefone selecionando **SwUpdate**.
  
![Captura de tela mostrando a opção SwUpdate](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
Você também pode optar por gerenciar atualizações de firmware usando um sistema de provisionamento de parceiros. Para gerenciamento de sistema de provisionamento de parceiros, incluindo personalização de telefone avançada, consulte guias de administração do fabricante.
  
> [!CAUTION]
> Verifique se você tem uma única autoridade de atualização de dispositivo (atualização de dispositivo em banda ou um servidor de provisionamento de terceiros) para evitar loops de atualização. 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a>Etapa 5-configurações e configurações de telefone de infraestrutura

Você pode configurar as opções de telefone mais usadas e políticas usando cmdlets do Windows PowerShell de gerenciamento em banda do Skype for Business. Consulte [set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx) para obter detalhes sobre esses parâmetros e configurações.
  
Para o planejamento de infraestrutura de rede, consulte a [estrutura de operações do Skype](https://www.skypeoperationsframework.com/).
  
### <a name="step-6---preparing-for-users-to-sign-in"></a>Etapa 6 – preparando para os usuários entrarem

Para permitir que os usuários se conectem com êxito a um telefone do Skype for Business Online e façam chamadas, você precisa ter certeza de que os usuários receberam as licenças corretas. No mínimo, você precisará atribuir uma licença do sistema de telefonia e um plano de chamada. Para obter informações adicionais, você pode ver [Licenciamento do complemento do Skype for Business e do Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) e [atribuir licenças do Skype for Business e do Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
  
Você pode saber mais sobre os planos de chamadas lendo [sistema telefônico e planos de chamada](/microsoftteams/calling-plan-landing-page)
  
- **As opções de entrada** que estão disponíveis para usuários online são:
    
  - Os usuários com os telefones **POLYCOM VVX 5xx/6xx** verão:
    
     ![Captura de tela mostrando o logon de telefones Polycom](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - Os usuários com os telefones **YEALINK T48G/T46G** verão:
    
     ![Captura de tela mostrando o logon de telefones Yealink.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    Para obter detalhes sobre as opções de entrada aceitas pelo fabricante, consulte [como obter telefones para o Skype for Business online](getting-phones-for-skype-for-business-online.md).
    
- **ID de usuário** Usando o teclado numérico do telefone ou o teclado virtual (se disponível), os usuários podem usar o nome de usuário e a senha da organização para entrar no telefone. Por exemplo, eles devem usar o formato UPN, como <em>amosm@contoso.com</em> para o nome de usuário dele.
    
     ![Captura de tela mostrando a tela de logon](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > Não há suporte para a autenticação de PIN no Skype for Business online para LPE e telefones IP de parceiros. 
  
- **Usando um computador** Quando o software da Ethernet (BToE) melhor está instalado no computador do usuário e habilitado, os usuários podem entrar em seus telefones usando a janela de autenticação no aplicativo Windows Skype for Business. Veja [a etapa 7 (opcional)-se você tiver o emparelhamento de dispositivos e melhor em conjunto com a Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) para obter outras informações.
    
  > [!NOTE]
  > Os usuários precisam usar o nome de usuário e a senha da organização para entrar no telefone. Por exemplo, eles devem usar o formato UPN, como <em>amosm@contoso.com</em> para o nome de usuário dele.
  
     ![Captura de tela mostrando a tela de logon](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- **Usando uma entrada na Web**: essa é uma nova maneira de os usuários online se autenticarem usando um navegador da Web padrão. Os usuários serão fornecidos com um conjunto de instruções a serem seguidas quando usarem um navegador para entrar.
    
  - Os usuários com os telefones **POLYCOM VVX 5xx/6xx** verão:
    
     ![Captura de tela mostrando as instruções Polycom](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - Os usuários com os telefones **YEALINK T48G/T46G** verão:
    
     ![Captura de tela mostrando instruções de Yealink](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    O código gerado irá expirar em 15 minutos. Quando ele expirar, o usuário terá que clicar em **repetir** ou em **OK** para gerar um novo código, dependendo do telefone.
    
  - Os usuários com os telefones **POLYCOM VVX 5xx/6xx** verão:
    
     ![Captura de tela mostrando o código Polycom expirado](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - Os usuários com os telefones **YEALINK T48G/T46G** verão:
    
     ![Captura de tela mostrando o código Yealink expirado](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    Usando um navegador, navegue até o endereço exibido no telefone e insira seu nome de usuário do Skype for Business.
    
     ![Captura de tela mostrando verificação de email](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    Digite o código exibido no telefone.
    
     ![Captura de tela mostrando a inserção do código na tela de logon](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    Verifique se o site mostra "[nome do fabricante do telefone] **telefone certificado pelo Skype for Business**" e clique em **continuar**.
    
     ![Captura de tela mostrando a verificação de nome](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    Clique nas credenciais do usuário ou clique em **usar outra conta**:
    
     ![Captura de tela mostrando opções de credenciais](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    Quando a página a seguir é exibida, é seguro fechar o navegador.
    
     ![Captura de tela mostrando a mensagem de confirmação](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > Telefones LPE para suporte do Skype for Business online com o compartilhamento somente para compartilhamento por USB. 
  
- **Implantações com suporte** A tabela a seguir mostra os tipos de autenticação com suporte para os modelos de implantação com suporte no momento, incluindo integração com o Exchange, autenticação moderna com autenticação multifator (MFA) e Skype for Business Online e local.
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Skype for Business** <br/> |**Exchange** <br/> |**Método de entrada no telefone** <br/> |**Acesso ao Skype for Business** <br/> |**Acesso do Exchange com autenticação moderna e MFA desabilitadas** <br/> |**Acesso do Exchange com autenticação moderna e MFA habilitados** <br/> |
|Online  <br/> |Online  <br/> |Entrada na Web  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |
|Online  <br/> |Online  <br/> |Nome de usuário/Senha  <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|Online  <br/> |Local  <br/> |Entrada na Web  <br/> |Sim  <br/> |Não  <br/> |Não  <br/> |
|Online  <br/> |Local  <br/> |Nome de usuário/Senha  <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|Local  <br/> |Online/local  <br/> |Autenticação de PIN  <br/> |Sim  <br/> |Não  <br/> |Não  <br/> |
|Local  <br/> |Online/local  <br/> |Nome de usuário/Senha  <br/> |Sim  <br/> |Sim  <br/> |N/D  <br/> |
|Local  <br/> |Online/local  <br/> |Entrada via PC (BTOE)  <br/> |Sim  <br/> |Sim  <br/> |N/D  <br/> |
   
- **Recursos de telefone** O conjunto de recursos pode variar um pouco de acordo com o parceiro de telefone IP. Para obter o conjunto de recursos completo e obter mais informações sobre os recursos para cada fabricante de telefone, consulte [como obter telefones para o Skype for Business online](getting-phones-for-skype-for-business-online.md).
    
- **Phone-Lock** é um recurso introduzido recentemente nos telefones certificados pelo Skype for Business que é usado para proteger um telefone. Se habilitada, os usuários serão solicitados a criar um PIN após uma autenticação bem-sucedida. Após a criação, os telefones serão bloqueados quando o tempo limite ocioso definido expirar, um usuário bloqueará manualmente o telefone ou sincronizará seus telefones com o bloqueio do computador usando o emparelhamento por telefone. Se o PIN de bloqueio de telefone for digitado várias vezes, o telefone desconectará o usuário ou exigirá um código de administrador para desbloquear o telefone, mas isso varia de acordo com o parceiro de telefone. O PIN do usuário deve ter entre 6 e 15 dígitos.
    
    Você pode desativar o bloqueio de telefone para sua organização (que é habilitado por padrão), alterar o tempo limite de ociosidade e escolher se os usuários podem fazer chamadas telefônicas enquanto estiverem bloqueados ou não usando as configurações de inband. Consulte [set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps) para obter mais detalhes sobre essas configurações.
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a>Etapa 7 (opcional)-se você tiver o emparelhamento de dispositivos e melhor em conjunto com a Ethernet (BToE)
<a name="BK_BTOE"> </a>

BToE é um mecanismo de inatividade do telefone para telefones IP do parceiro que emparelham o telefone de um usuário com o aplicativo do Windows Skype for Business. O BToE permite que os usuários:
  
- Entre em seu telefone IP usando o aplicativo da área de trabalho do Skype for Business (usando um PC)
    
- Sincronizar o telefone-bloquear com o bloqueio do computador
    
- Clicar para chamar
    
O BToE pode ser configurado para operar em dois modos: *automático* (padrão) e *manual* . Ele também pode ser habilitado (padrão)/Disabled para usuários que usam as configurações em banda do Skype for Business. Ao operar no modo *manual* , os usuários precisarão fazer uma etapa adicional para emparelhar o telefone com o aplicativo do Windows.
  
 **Para implantar o BToE para os usuários**
  
1. Conecte o computador ao telefone usando a porta do computador.
    
     ![Captura de tela mostrando conexão a um PC](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. Baixe e instale o software BToE mais recente do website do fabricante nos links abaixo. Para ter uma experiência de usuário melhor, você pode distribuir e instalar o software BToE usando uma solução de distribuição de administração, como o Gerenciador de configuração do Microsoft Endpoint. Para obter ajuda sobre como usar o Configuration Manager, consulte [pacotes e programas no Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).
    
   - [Site de download de software do Polycom BToE](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [Download de software do Yealink BToE](http://www.yealink.com/products_list_10.html)
    
   - [Downloads de software do AudioCodes BToE](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. A configuração do servidor para BToE é definida como **Enabled** e **modo automático** por padrão. Para alterar essas configurações, consulte [set-CsIPPhonePolicy](https://technet.microsoft.com/library/mt629497.aspx).
    
> [!NOTE]
> BToE atualmente não é compatível com plataformas Mac e VDI. 
  
## <a name="related-topics"></a>Tópicos relacionados
[Obtendo números de telefone de serviço do Skype for Business e do Microsoft Teams](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[Veja aqui o que você obtém com o Sistema de Telefonia no Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Disponibilidade da Audioconferência e dos Planos de Chamadas por país e região](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
