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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: Saiba as etapas de implantação para obter o firmware correto, atualizá-lo, se necessário, atribuir licenças e configurar configurações para Skype for Business telefones online
ms.openlocfilehash: d67badf0bd5ff27466315a5731c2ac9a2117f74e
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728010"
---
# <a name="deploying-skype-for-business-online-phones"></a>Implantando telefones do Skype for Business Online

[!INCLUDE [sfbo-retirement](../../../Hub/includes/sfbo-retirement.md)]

Este é o guia de implantação que o ajudará a implantar Skype for Business ip online.
  
Em todos os tipos de empresas, ter um número de telefone permite que os usuários façam e recebam chamadas de voz, e é um requisito importante para fazer negócios. Os usuários que têm números de telefone poderão fazer chamadas de voz em todos os Skype for Business, incluindo telefones IP, computadores e dispositivos móveis. Você pode saber mais sobre os Skype for Business IP lendo Obter telefones para Skype for Business [Online.](getting-phones-for-skype-for-business-online.md)
  
## <a name="deployment-steps-for-ip-phones"></a>Etapas de implantação para telefones IP

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a>Etapa 1 - Baixar guias de administrador e manuais de telefone do fabricante

Antes de começar, é uma boa ideia baixar os guias de administração do fabricante do telefone e manuais do usuário do telefone.
  
- Para telefones Polycom, consulte [a Biblioteca de Documentação Poly.](https://documents.polycom.com/category/voice)
    
- Para telefones Yealink, consulte [Yealink Skype for Business HD SIP Phones Solution](http://www.yealink.com/products_top_2.html).
    
- Para telefones AudioCodes, consulte o Guia de Gerenciamento de Provisionamento de [Audiocódigos.](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a>Etapa 2 : certifique-se de que você está comprando ou migrando um telefone IP e firmware com suporte Skype for Business ip com suporte

Um Skype for Business e firmware compatíveis com o Skype for Business Server online também são compatíveis com o Skype for Business Server, mas o oposto nem sempre é verdadeiro. Para garantir que você está comprando ou provisionando um telefone e firmware com suporte, consulte [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a>Etapa 3 - Verificar se o firmware certo está instalado e atualizar o firmware, se necessário

Verifique a versão do firmware em seus telefones. Para:
  
- **Telefones Polycom VVX**, acesse **Configurações** Aplicativo Principal da Plataforma  >    >    >  **de**  >  **Status.**
    
- **Telefones yealink**, vá para **Status** na tela do telefone principal.
    
- **AudioCodes telefones**, vá para **Menu** Versão do Firmware de Status do Dispositivo  >    >   na tela inicial.
    
    > [!NOTE]
    > Para obter acesso remoto aos detalhes do telefone, consulte guias de administração do fabricante. Consulte os links acima para os guias de usuário e manuais de telefone. 
  
- **Telefones do Lync Telefone Edition (LPE),** acesse **Menu**  >  **Informações do Sistema** da tela inicial.
    
### <a name="step-4---device-update-considerations"></a>Etapa 4 - Considerações sobre atualização de dispositivos

> [!NOTE]
> O firmware polycom antes do 5.5.1.X tinha um mecanismo de bloqueio de dispositivo específico do fabricante que é substituído por uma implementação Skype for Business "Telefone-Lock". Atualizar um telefone de 5.4.X.X que foi protegido com "Device-Lock" para 5.5.1.X com "Telefone-Lock" não herdará o código PIN de "Device-Lock", o que pode deixar o telefone sem segurança. Os usuários que ativaram o "Device-Lock" precisam habilitar o seguinte parâmetro Polycom Device Profile para dar aos usuários o controle do tempo de atualização (lync.deviceUpdate.popUpSK.enabled=1). 
  
As atualizações de firmware são gerenciadas pelo Skype for Business Service. Todo firmware de telefone certificado pelo Skype for Business é carregado para o servidor de atualização do Skype for Business e a atualização do dispositivo é habilitada em todos os telefones por padrão. Dependendo do tempo de inatividade no telefone e dos intervalos de sondagem, os telefones baixarão e instalarão automaticamente as versões certificadas mais recentes. Você pode desabilitar as configurações de atualização do dispositivo usando o cmdlet [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy) e definindo o _parâmetro EnableDeviceUpdate_ como `false` .
  
![Captura de tela mostrando a implantação de telefones.](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
Quando um novo firmware estiver disponível e pronto para download e instalação, o telefone notificará o usuário. Os telefones Polycom notificarão o usuário e fornecerão uma opção para **Atualizar** ou **Adiar**.
  
![Captura de tela mostrando opções de Atualização e Adiamento.](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
Para um telefone Polycom, você pode atualizar o firmware no telefone selecionando **SwUpdate**.
  
![Captura de tela mostrando a opção SwUpdate.](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
Você também pode optar por gerenciar atualizações de firmware usando um sistema de provisionamento de parceiros. Para gerenciamento do sistema de provisionamento de parceiros, incluindo personalização avançada de telefone, consulte guias de administração do fabricante.
  
> [!CAUTION]
> Certifique-se de ter uma única autoridade de atualização de dispositivo (atualização de dispositivo em banda ou um servidor de provisionamento de terceiros) para evitar loops de atualização. 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a>Etapa 5 - Configuração e configurações de telefone de infraestrutura

Você pode configurar as opções e políticas de telefone mais comumente usadas usando Skype for Business gerenciamento em banda Windows PowerShell cmdlets. Consulte [Set-CsIPPhonePolicy para](/powershell/module/skype/Set-CsIPPhonePolicy) obter detalhes desses parâmetros e configurações.
  
Para planejar a infraestrutura de rede, [consulte Skype Operations Framework](https://www.skypeoperationsframework.com/).
  
### <a name="step-6---preparing-for-users-to-sign-in"></a>Etapa 6 - Preparando os usuários para entrar

Para habilitar os usuários a entrar com êxito em um telefone Skype for Business Online e fazer chamadas, você precisa garantir que os usuários sejam atribuídos às licenças corretas. No mínimo, você precisará atribuir uma licença de Sistema de Telefonia e um Plano de Chamada. Para obter informações adicionais, você pode [ver Skype for Business](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) e Microsoft Teams licenciamento de complemento e Atribuir Skype for Business e [Microsoft Teams licenças](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
  
Você pode saber mais sobre Planos de Chamada lendo Sistema de Telefonia [e Planos de Chamada](/microsoftteams/calling-plan-landing-page)
  
- **As opções de login** disponíveis para usuários online são:
    
  - Os usuários **com telefones Polycom VVX 5XX/6XX** verão:
    
     ![Captura de tela mostrando o logon de telefones Polycom.](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - Os usuários **com telefones Yealink T48G/T46G** verão:
    
     ![Captura de tela mostrando o logon de telefones Yealink.](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    Para obter detalhes sobre as opções de login com suporte do fabricante, consulte [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).
    
- **ID do usuário** Usando o teclado do telefone ou o teclado na tela (se disponível), os usuários podem usar o nome de usuário e a senha da organização para entrar no telefone. Por exemplo, eles devem usar o formato UPN como <em>amosm@contoso.com</em>  para seu nome de usuário.
    
     ![Captura de tela mostrando a tela de logon.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > A autenticação de PIN não é suportada para o Skype for Business Online para telefones IP de parceiros e LPE. 
  
- **Usando um computador** Quando o software Better Together over Ethernet (BToE) é instalado no computador do usuário e habilitado, os usuários podem fazer logoff em seus telefones usando a janela de autenticação em seu Windows Skype for Business App. Consulte a Etapa 7 (opcional) - Se você tiver emparelhamento de dispositivos e [Melhor Juntos sobre Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) para obter outras informações.
    
  > [!NOTE]
  > Os usuários devem usar o nome de usuário e a senha de sua organização para entrar no telefone. Por exemplo, eles devem usar o formato UPN como  <em>amosm@contoso.com</em>  para seu nome de usuário.
  
     ![Captura de tela mostrando a tela de logon.](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- **Usando um Web Sign-in**: Essa é uma nova maneira para os usuários online autenticar usando um navegador da Web padrão. Os usuários receberão um conjunto de instruções a seguir quando usarem um navegador para entrar.
    
  - Os usuários **com telefones Polycom VVX 5XX/6XX** verão:
    
     ![Captura de tela mostrando as instruções polycom.](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - Os usuários **com telefones Yealink T48G/T46G** verão:
    
     ![Captura de tela mostrando instruções yealink.](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    O código gerado expirará em 15 minutos. Quando expirar, o usuário terá que clicar em **Repetir** ou **OK** para gerar um novo código, dependendo do telefone.
    
  - Os usuários **com telefones Polycom VVX 5XX/6XX** verão:
    
     ![Captura de tela mostrando código Polycom expirado.](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - Os usuários **com telefones Yealink T48G/T46G** verão:
    
     ![Captura de tela mostrando código Yealink expirado.](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    Usando um navegador, navegue até o endereço exibido no telefone e insira seu nome Skype for Business nome de usuário.
    
     ![Captura de tela mostrando verificação de email.](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    Insira o código mostrado no telefone.
    
     ![Captura de tela mostrando a inserção de código na tela de logon.](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    Verifique se o site mostra "[Telefone Nome do fabricante] **Skype for Business certificado Telefone**", e clique em **Continuar**.
    
     ![Captura de tela mostrando a verificação do nome.](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    Clique nas credenciais do usuário ou clique em **Usar outra conta:**
    
     ![Captura de tela mostrando opções de credencial.](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    Quando a página a seguir é exibida, é seguro fechar o navegador.
    
     ![Captura de tela mostrando mensagem de confirmação.](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > Telefones LPE para Skype for Business online suportam entrada somente por meio de conexão USB. 
  
- **Implantações com suporte** A tabela a seguir mostra os tipos de autenticação com suporte para os modelos de implantação atualmente suportados, incluindo integração Exchange, autenticação moderna com MFA (Autenticação multifatória) e Skype for Business Online e local.
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Skype for Business** <br/> |**Exchange** <br/> |**Telefone Sign-In método** <br/> |**Skype for Business acesso** <br/> |**Exchange Acesso com Auth Moderno e MFA desabilitado** <br/> |**Exchange Acesso com a Auth Moderna e MFA habilitada** <br/> |
|Online  <br/> |Online  <br/> |Web Sign-in  <br/> |Sim  <br/> |Sim  <br/> |Sim  <br/> |
|Online  <br/> |Online  <br/> |Nome de usuário/Senha  <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|Online  <br/> |Local  <br/> |Web Sign-in  <br/> |Sim  <br/> |Não  <br/> |Não  <br/> |
|Online  <br/> |Local  <br/> |Nome de usuário/Senha  <br/> |Sim  <br/> |Sim  <br/> |Não  <br/> |
|Local  <br/> |Online/local  <br/> |Autenticação PIN  <br/> |Sim  <br/> |Não  <br/> |Não  <br/> |
|Local  <br/> |Online/local  <br/> |Nome de usuário/Senha  <br/> |Sim  <br/> |Sim  <br/> |N/D  <br/> |
|Local  <br/> |Online/local  <br/> |Entrar por computador (BTOE)  <br/> |Sim  <br/> |Sim  <br/> |N/D  <br/> |
   
- **Telefone recursos** O conjunto de recursos pode variar ligeiramente com base no parceiro de telefone IP. Para obter o conjunto de recursos completo e para obter mais informações sobre os recursos para cada fabricante de telefone, consulte Obter telefones [para Skype for Business Online](getting-phones-for-skype-for-business-online.md).
    
- **Telefone-Lock** é um recurso introduzido recentemente em Skype for Business certificados que é usado para proteger um telefone. Se habilitado, os usuários serão solicitados a criar um PIN após a autenticação bem-sucedida. Depois de criados, os telefones serão travados quando o tempo de ociosidade definido expirar, um usuário bloqueará manualmente seu telefone ou sincronizará o bloqueio de telefone com o bloqueio do computador usando o Telefone Emparelhamento. Se o PIN de bloqueio de telefone for inserido errado várias vezes, o telefone assinará o usuário ou exigirá o código de um administrador para desbloquear o telefone, mas isso variará dependendo do parceiro de telefone. O PIN do usuário deve ter entre 6 e 15 dígitos.
    
    Você pode desabilitar Phone-Lock para sua organização (que está habilitada por padrão), alterar o tempo de ociosidade e escolher se os usuários podem fazer chamadas telefônicas enquanto estão bloqueados ou não usando configurações de banda interna. Consulte [Set-CsUCPhoneConfiguration](/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps) para obter mais detalhes sobre essas configurações.
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a>Etapa 7 (opcional) - Se você tiver emparelhamento de dispositivos e Melhor Juntos sobre Ethernet (BToE)
<a name="BK_BTOE"> </a>

BToE é um mecanismo de dor de telefone para telefones IP parceiros que emparelha o telefone de um usuário com seu Windows Skype for Business aplicativo. BToE permite que os usuários:
  
- Entre no telefone IP usando seu aplicativo Skype for Business desktop (usando um computador)
    
- Sincronizar Phone-Lock com bloqueio de computador
    
- Clique para chamar
    
O BToE pode ser configurado para operar em dois modos:  *Automático*  (padrão) e *Manual*  . Ele também pode ser habilitado (padrão)/desabilitado para usuários que Skype for Business configurações em banda. Ao operar no *modo Manual,* os usuários terão que dar uma etapa adicional para emparelhar seu telefone com seu Windows aplicativo.
  
 **Para implantar o BToE aos usuários**
  
1. Conexão seu computador para o telefone usando a porta do computador.
    
     ![Captura de tela mostrando conexão com um computador.](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. Baixe e instale o software BToE mais recente do site do fabricante nos links abaixo. Para uma melhor experiência do usuário, você pode distribuir e instalar o software BToE usando uma solução de distribuição de administrador, como Microsoft Endpoint Configuration Manager. Para saber mais sobre como usar o Configuration Manager, consulte [Pacotes e programas no Configuration Manager.](/configmgr/apps/deploy-use/packages-and-programs)
    
   - [Site de download de software do Polycom BToE](https://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [Yealink BToE Software Download](http://www.yealink.com/products_list_10.html)
    
   - [AudioCodes BToE Software Downloads](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. A configuração do servidor para BToE é definida como **Habilitado e** **Modo Automático** por padrão. Para alterar essas configurações, consulte [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy).
    
> [!NOTE]
> No momento, o BToE não tem suporte em plataformas Mac e VDI. 
  
## <a name="related-topics"></a>Tópicos relacionados
[Obtendo números de telefone de serviço do Skype for Business e do Microsoft Teams](/microsoftteams/getting-service-phone-numbers)

[Veja o que você obtém com o Sistema de Telefonia](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Disponibilidade de Audioconferência e Planos de Chamadas por país e região](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
