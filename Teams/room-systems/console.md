---
title: Configurar um console de salas do Microsoft Teams
ms.author: v-lanac
author: lanachin
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: Este artigo descreve como configurar o console de salas do Microsoft Teams e seus periféricos.
ms.openlocfilehash: 6172e37b53934bc75ae7f5bdf848fd503ffe2e8a
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/16/2019
ms.locfileid: "38675769"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a>Configurar um console de salas do Microsoft Teams

Este artigo descreve como configurar o console de salas do Microsoft Teams e seus periféricos.
  
Você deve executar essas etapas somente se as contas necessárias do Microsoft Teams ou do Skype for Business e do Exchange já tiverem sido criadas e testadas, conforme descrito em [implantar salas do Microsoft Teams](room-systems-v2.md). Você precisará do hardware e do software descritos nos [requisitos de sala do Microsoft Teams](requirements.md). Este tópico inclui as seguintes seções:
  
- [Preparar a mídia de instalação](console.md#Prep_Media)
- [Instalar um certificado de autoridade de certificação particular no console](console.md#Certs)
- [Instalar o Windows 10 e o aplicativo de console de salas do Microsoft Teams](console.md#Reimage)
- [Configuração inicial do console](console.md#Initial)
- [Lista de verificação de implantação de salas do Microsoft Teams](console.md#Checklist)

> [!NOTE]
> As salas do Microsoft Teams funcionarão apenas em um ambiente do Microsoft Teams ou do Skype for Business configurado corretamente, em que as contas do dispositivo são configuradas corretamente, conforme descrito em [implantar salas do Microsoft Teams](room-systems-v2.md).
  
## <a name="prepare-the-installation-media"></a>Preparar a mídia de instalação
<a name="Prep_Media"> </a>

A instalação do aplicativo de console de salas do Microsoft Teams requer um dispositivo de armazenamento USB com pelo menos 32GB de capacidade. Não deve haver outros arquivos no dispositivo; qualquer arquivo existente no armazenamento USB será perdido.
  
> [!NOTE]
> Falha ao criar a mídia de instalação das salas do Microsoft Teams, de acordo com essas instruções, provavelmente resultará em um comportamento inesperado.

> [!NOTE]
> O processo abaixo destina-se à criação de mídia de instalação em imagens de novos dispositivos de sala do Microsoft Teams. Os dispositivos existentes, por padrão, são atualizados automaticamente no Windows Update e na Windows Store.
  
1. Baixe o [script CreateSrsMedia. ps1](https://go.microsoft.com/fwlink/?linkid=867842).
2. Execute o script CreateSrsMedia.ps1 de um prompt com privilégios elevados em um computador Windows 10.
3. Siga as instruções do script para criar um disco de instalação USB de salas do Microsoft Teams.


> [!TIP]
> Toda vez que o script CreateSrsMedia. ps1 for iniciado, a saída da tela incluirá o nome de um arquivo de log ou transcrição para a sessão. Se houver problemas com a execução do script, certifique-se de ter uma cópia dessa transcrição disponível ao solicitar suporte. 

O script CreateSrsMedia. ps1 automatiza as seguintes tarefas:

1. Baixe a versão mais recente do MSI Installer para salas do Microsoft Teams.
2. Determine a compilação do Windows que o usuário deve fornecer. As versões lançadas mais recentemente podem ou não ser testadas e com suporte para uso com dispositivos de salas do Microsoft Teams.
3. Baixe os componentes de suporte necessários.
4. Monte os componentes necessários na mídia de instalação.

Uma versão específica do Windows 10 é necessária, e essa versão só está disponível para clientes de licenciamento por volume.  Você pode obter uma cópia do [centro de serviços de licenciamento por volume](https://www.microsoft.com/Licensing/servicecenter/).

Quando terminar, remova o disco USB do computador e prossiga para [instalar o Windows 10 e o aplicativo de console de salas do Microsoft Teams](console.md#Reimage).

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Instalar o Windows 10 e o aplicativo de console de salas do Microsoft Teams
<a name="Reimage"> </a>

Agora, você precisa aplicar a mídia de configuração que você criou. O dispositivo de destino será executado como um dispositivo e o usuário padrão será definido para executar somente o aplicativo de console de salas do Microsoft Teams.

1. Se o dispositivo de destino for instalado em um Dock (por exemplo, um Surface pro), desconecte-o do Dock.

2. Verifique se o dispositivo de destino não está conectado à rede.

3. Verifique se o dispositivo de destino está conectado à alimentação de CA.

4. Conecte o disco de instalação USB ao dispositivo de destino.

5. Inicialize no disco de instalação USB. Consulte as instruções do fabricante. Se o seu dispositivo de destino for um Surface pro, use as seguintes etapas para inicializar o disco de instalação USB:

    a. Pressione e continue a manter pressionado o botão Volume Down (-).

    b. Pressione e libere o botão de energia.

    c. Depois que a instalação do Windows for inicializada, solte o botão de abaixar o volume (-).

8. O sistema será desligado após a conclusão da instalação.
    
Após o sistema ser desligado, é seguro remover o disco de instalação USB. Nesse ponto, você pode colocar o dispositivo de destino em seu Dock (se estiver usando um produto baseado em encaixe), anexar os periféricos necessários para a sala de reunião e se conectar à rede. Consulte as instruções do fabricante.

> [!NOTE]
> As atualizações de software para salas do Microsoft Teams são automaticamente baixadas da Microsoft Store para empresas. Veja [pré-requisitos para a Microsoft Store para empresas e instituições de ensino](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) para verificar se o console da sala poderá acessar a loja e a atualização automática.  

### <a name="selecting-a-language"></a>Selecionando um idioma 

Na atualização do criador, você precisará usar o script ApplyCurrentRegionAndLanguage. ps1 em cenários em que a seleção de idioma implícita não forneça ao usuário o idioma real do aplicativo desejado (por exemplo, que eles querem que o aplicativo de console seja exibido em francês, mas Ele está chegando em inglês).
  
> [!NOTE]
> As instruções a seguir funcionam apenas para consoles criados usando a atualização do criador do Windows. Sistemas herdados/no mercado que não foram configurados usando mídia com o novo sistema de provisionamento não poderão usar essas instruções, mas também não devem ser de acordo com o problema inicial que exige essa intervenção manual (a edição de aniversário permite que você escolha o idioma do aplicativo explicitamente como parte da instalação).
  
### <a name="to-apply-your-desired-language"></a>Para aplicar o idioma desejado

1. Mude para o modo de Administrador.
    
2. Selecione o menu Iniciar.
    
3. Selecione o ícone de engrenagem para iniciar o aplicativo de **Configurações**.
    
4. Selecione **o &amp; idioma do tempo**.
    
5. Selecione **idioma &amp; da região**.
    
6. Selecione **Adicionar um idioma**.
    
7. Selecione o idioma que deseja adicionar.
    
8. Selecione o idioma que você acabou de adicionar à lista "idiomas".
    
9. Selecione **Definir como padrão**.
    
10. Para idiomas que deseja remover:
    
    a. Selecione o idioma que deseja remover.
    
    b. Selecione **Remover**.
    
11. Inicie um prompt de comandos com privilégios elevados.
    
12. Execute o seguinte comando: 
    ```
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. Reinicie o sistema.
    
O idioma desejado agora está aplicado ao console de salas do Microsoft Teams.
## <a name="initial-set-up-of-the-console"></a>Configuração inicial do console
<a name="Initial"> </a>

Após a instalação do Windows, o aplicativo de console de salas do Microsoft Teams entrará em seu processo inicial de configuração quando for iniciado em seguida, ou se a opção/reboot tiver sido escolhida.
  
1. A tela Conta de Usuário é exibida. Digite o endereço de entrada do Skype (no formato user@domain) da conta da sala a ser usada com o console.
    
2. Digite a senha para a conta da sala e digite-a novamente para verificar.
    
3. Em "configurar domínio", defina o FQDN do Skype for Business Server. Se o domínio SIP do Skype for Business for diferente do domínio do Exchange do usuário, insira o domínio do Exchange nesse campo.
    
4. Click **Next**.
    
5. Selecione os dispositivos indicados na tela recursos e clique em **Avançar**. O padrão é ter o compartilhamento automático de tela definido como Ativado e Ocultar os nomes da reunião definido como Desativado. Os dispositivos para selecionar são:
    
   - Microfone para conferência: o microfone padrão para a sala de conferência.
    
   - Alto-falante para conferência: o alto-falante padrão para conferência  
    
   - Alto-falante padrão: o alto-falante usado para áudio da ingestão HDMI.
    
     Cada item tem um menu suspenso de opção para seleção. Você deve fazer uma seleção para cada dispositivo.
    
6. Clique em **Concluir**.
    
O aplicativo de console de salas do Microsoft Teams deve começar imediatamente a entrar no Skype for Business Server com as credenciais inseridas acima e também deve começar a sincronizar seu calendário com o Exchange usando essas mesmas credenciais. Para obter detalhes sobre como usar o aplicativo console, consulte a [ajuda de salas do Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).
  
> [!IMPORTANT]
> Salas do Microsoft Teams depende da presença de hardware de console certificado. Até mesmo uma imagem criada corretamente contendo o aplicativo de console de salas do Microsoft Teams não será inicializada após o procedimento de configuração inicial, a menos que o hardware do console seja detectado. Para soluções com base em Surface pro, o Surface pro deve estar conectado ao seu equipamento de encaixe que o acompanha para transmitir essa verificação.
  
> [!NOTE]
> Alguns usuários do idioma diferente do inglês podem precisar de um teclado físico conectado ao console durante a configuração inicial, caso os símbolos não sejam compatíveis com o teclado virtual.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>Instalar um certificado de autoridade de certificação particular no console
<a name="Certs"> </a>

O console de salas do Microsoft Teams precisa confiar nos certificados usados pelos servidores aos quais ele se conecta. No O365, isso é feito automaticamente, pois esses servidores usam Autoridades de Certificação públicas e o Windows 10 confia nelas automaticamente. Em um caso em que a autoridade de certificação é particular, por exemplo, uma implantação local com o Active Directory e a autoridade de certificação do Windows, você pode adicionar o certificado ao console de salas do Microsoft Teams de algumas maneiras:
  
- Você pode ingressar no console no Active Directory e isso adicionará automaticamente os certificados obrigatórios, uma vez que a autoridade de certificação seja publicada no Active Directory (opção de implantação normal).
    
- Você pode instalar o certificado manualmente após o processo de geração de imagens. Antes de fazer isso, você deve concluir [a configuração inicial do console](console.md#Initial).
    
### <a name="to-manually-install-the-certificate"></a>Para instalar o certificado manualmente 

1. Baixe o certificado de autoridade de certificação para seu computador e salve-o em "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".
    
2. Colocar o console no modo de administração (consulte o [modo de administrador e o gerenciamento de dispositivos](room-systems-v2-operations.md#AdminMode)).
    
3. Execute o seguinte comando:
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Ingressar em um domínio do Active Directory (opcional)
<a name="Certs"> </a>

Você pode ingressar nos consoles de salas do Microsoft Teams no seu domínio. Os consoles de salas do Microsoft Teams devem ser colocados em uma UO separada a partir de suas estações de trabalho de PC porque muitas políticas de estação de trabalho não são compatíveis com as salas do Microsoft Teams. Um exemplo comum são as políticas de imposição de senha que impedem o início automático das salas do Microsoft Teams. Para obter informações sobre o gerenciamento de configurações de GPO, consulte [gerenciar salas do Microsoft Teams](room-systems-v2-operations.md).
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>Para ingressar em salas do Microsoft Teams em um domínio

1. Conecte-se ao console da conta de administrador (consulte o [modo de administrador e o gerenciamento de dispositivos](room-systems-v2-operations.md#AdminMode)).
    
2. Inicie o comando em um prompt de comandos com privilégios elevados do Powershell.
    
3. Digite o seguinte comando no Powershell:
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

Por exemplo, se o seu domínio totalmente qualificado for redmond.corp.microsoft.com e você quiser que seus consoles de salas do Microsoft Team estejam em uma UO "salas do Microsoft Teams" que seja filho de uma OU "recursos", o comando será:
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 Se você quiser renomear o computador ao ingressar em um domínio, use o sinalizador-NewName seguido pelo nome novo do computador.
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Lista de verificação de implantação de salas do Microsoft Teams
<a name="Checklist"> </a>

Use a lista de verificação a seguir ao fazer uma verificação final de que o console e todos os seus periféricos estão totalmente configurados:
  
**Configurações do aplicativo**

|||
|:-----|:-----|
|☐  <br/> |O Nome e o número de telefone da conta da sala (se PSTN estiver habilitado) são exibidos corretamente na parte superior direita da tela do console  <br/> |
|☐  <br/> |O nome do computador Windows está definido corretamente (útil para administração remota)  <br/> |
|☐  <br/> |A senha da conta do administrador foi definida e verificada  <br/> |
|☐  <br/> |Todas as atualizações de firmware foram aplicadas  <br/> |
   
**Periféricos de áudio/vídeo**

|||
|:-----|:-----|
|☐  <br/> |A versão do firmware do periférico da câmera está correta (se aplicável)  <br/> |
|☐  <br/> |Câmera funcional e posicionada da maneira ideal  <br/> |
|☐  <br/> |Configurações para o Dispositivo de Reprodução Padrão e o Dispositivo de Comunicações Padrão definidas para o periférico de áudio desejado  <br/> |
|☐  <br/> |Configurações para Registrar o Dispositivo de Comunicação Padrão definidas para o periférico de áudio desejado  <br/> |
|☐  <br/> |A versão do firmware do periférico de áudio está correta (se aplicável)  <br/> |
|☐  <br/> |Dispositivo de entrada de áudio funcional e posicionado corretamente  <br/> |
|☐  <br/> |Dispositivo de saída de áudio funcional e posicionado corretamente  <br/> |
   
**Encaixe**

|||
|:-----|:-----|
|☐  <br/> |Os cabos estão presos e não estão dobrados  <br/> |
|☐  <br/> |Ingestão de áudio via HDMI funcional  <br/> |
|☐  <br/> |Ingestão de vídeo via HDMI funcional  <br/> |
|☐  <br/> |O encaixe pode girar livremente  <br/> |
|☐  <br/> |O brilho da tela é aceitável para o ambiente  <br/> |
   
## <a name="see-also"></a>Confira também
<a name="Checklist"> </a>

[Plano para salas do Microsoft Teams](skype-room-systems-v2-0.md)
  
[Implantar salas do Microsoft Teams](room-systems-v2.md)
  
[Configurar um console de salas do Microsoft Teams](console.md)
  
[Gerenciar Salas do Microsoft Teams](skype-room-systems-v2.md)
