---
title: Criar uma Salas do Microsoft Teams imagem
ms.author: czawideh
author: cazawideh
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: Este artigo descreve como configurar e configurar o console Salas do Microsoft Teams e seus periféricos.
ms.openlocfilehash: 42f10ffe4ed2b577e91ed13b57ea8efcae67a1a4
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63504008"
---
# <a name="build-a-microsoft-teams-rooms-image"></a>Criar uma Salas do Microsoft Teams imagem

Este artigo descreve como criar uma imagem Salas do Microsoft Teams para implantação em massa de Salas do Teams.

> [!NOTE]
> As etapas a seguir só devem ser usadas ao criar uma [imagem baseada em WIM](/windows-hardware/manufacture/desktop/capture-and-apply-an-image) para implantação em massa. Se você estiver recuperando dispositivos individuais, entre em contato com o Fabricante de Equipamento Original (OEM) para ter suporte.

Você só deve executar essas etapas se as contas Microsoft Teams ou Skype for Business e Exchange já foram criadas e testadas conforme descrito em [Deploy Salas do Microsoft Teams](rooms-deploy.md). Você precisará do hardware e software descritos em Salas do Microsoft Teams [requisitos](requirements.md). Este tópico inclui as seguintes seções:
  
- [Preparar a mídia de instalação](console.md#Prep_Media)
- [Instalar um certificado ca privado no console](console.md#Certs)
- [Instalar Windows 10 e o aplicativo Salas do Microsoft Teams console do Salas do Microsoft Teams](console.md#Reimage)
- [Configuração inicial do console](console.md#Initial)
- [Salas do Microsoft Teams lista de verificação de implantação](console.md#Checklist)

## <a name="prepare-the-installation-media"></a>Preparar a mídia de instalação
<a name="Prep_Media"> </a>

Instalar o aplicativo Salas do Microsoft Teams console requer um dispositivo de armazenamento USB com pelo menos 32 GB de capacidade. Não deve haver outros arquivos no dispositivo; todos os arquivos existentes no armazenamento USB serão perdidos.
  
> [!NOTE]
> A falha ao criar sua Salas do Microsoft Teams de instalação de acordo com essas instruções provavelmente resultará em comportamento inesperado.

> [!NOTE]
> O processo a seguir é para criar mídia de instalação para imagem de novos Salas do Microsoft Teams dispositivos. Dispositivos existentes, por padrão, são atualizados automaticamente Windows Atualização e o Windows Store.

> [!IMPORTANT]
> O Windows 10 usado para criar a mídia de instalação Salas do Microsoft Teams deve estar na mesma versão ou posterior do Windows que a mídia de instalação de destino.
  
1. Baixe o [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).
2. Execute o script CreateSrsMedia.ps1 de um prompt com privilégios elevados em um computador Windows 10.
3. Siga as instruções do script para criar um disco Salas do Microsoft Teams configuração USB.


> [!TIP]
> Sempre que o script CreateSrsMedia.ps1 for iniciado, a saída de tela incluirá o nome de um arquivo de log ou transcrição da sessão. Se houver problemas com a execução do script, certifique-se de ter uma cópia dessa transcrição disponível ao solicitar suporte. 

O CreateSrsMedia.ps1 script automatiza as seguintes tarefas:

1. Baixe o instalador MSI mais recente para Salas do Microsoft Teams.
2. Determine a com Windows que o usuário deve fornecer. As versões lançadas mais recentemente podem ou não ser testadas e suportadas para uso com Salas do Microsoft Teams dispositivos.
3. Baixe os componentes de suporte necessários.
4. Montar os componentes necessários na mídia de instalação.

> [!NOTE]
Uma versão específica do Windows 10 é necessária, e essa versão só está disponível para clientes de licenciamento por volume.  Você pode obter uma cópia do Centro de Serviços [de Licenciamento por Volume](https://www.microsoft.com/Licensing/servicecenter/).

Quando terminar, remova o disco USB do computador e prossiga para [Instalar Windows 10 e o aplicativo Salas do Microsoft Teams console.](console.md#Reimage)

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Instalar Windows 10 e o aplicativo Salas do Microsoft Teams console do Salas do Microsoft Teams
<a name="Reimage"> </a>

Agora você precisa aplicar a mídia de instalação criada. O dispositivo de destino será executado como um dispositivo e o usuário padrão será definido para executar apenas o Salas do Microsoft Teams aplicativo.

1. Se o dispositivo de destino for instalado em um dock (por exemplo, um Surface Pro), desconecte-o do dock.

2. Verifique se o dispositivo de destino não está conectado à rede.

3. Verifique se o dispositivo de destino está conectado à energia ac.

4. Conecte seu disco de configuração USB ao dispositivo de destino.

5. Inicializar no disco de configuração USB. Consulte as instruções do fabricante. Se o dispositivo de destino for um Surface Pro, use as etapas a seguir para inicializar no disco de configuração USB:

    a. Pressione e continue a segurar o botão de volume para baixo (-).

    b. Pressione e solte o botão de energia.

    c. Depois que a instalação do Windows for inicializada, solte o botão de abaixar o volume (-).

8. O sistema será desligado depois que a instalação for concluída.
    
Depois que o sistema for desligado, é seguro remover o disco de configuração USB. Neste ponto, você pode colocar o dispositivo de destino em seu encaixe (se estiver usando um produto baseado em dock), anexar os periféricos necessários para sua sala de reunião e se conectar à rede. Consulte as instruções do fabricante.

> [!NOTE]
> As atualizações de software Salas do Microsoft Teams são baixadas automaticamente do Microsoft Store para Empresas. Consulte [Pré-requisitos para Microsoft Store para Empresas e Education](/microsoft-store/prerequisites-microsoft-store-for-business) para verificar se o console de sala será capaz de acessar a loja e a atualização automática.  

### <a name="selecting-a-language"></a>Selecionar um idioma 

Na Atualização do Criador, você precisará usar o script ApplyCurrentRegionAndLanguage.ps1 em cenários em que a seleção implícita de idioma não fornece ao usuário o idioma real do aplicativo que deseja (por exemplo, eles querem que o aplicativo de console seja usado em francês, mas está chegando em inglês).
  
> [!NOTE]
> As instruções a seguir funcionam apenas para consoles criados Windows Atualização do Criador (Windows 10 20H1) ou posterior.
  
### <a name="to-apply-your-desired-language"></a>Para aplicar o idioma desejado

1. Mude para o modo de Administrador.
    
2. Selecione o menu Iniciar.
    
3. Selecione o ícone de engrenagem para iniciar o aplicativo de **Configurações**.
    
4. Selecione **Idioma hora&amp;**.
    
5. Selecione **Idioma de &amp; região**.
    
6. Selecione **Adicionar um idioma**.
    
7. Selecione o idioma que deseja adicionar.
    
8. Selecione o idioma que você acabou de adicionar à lista "Idiomas".
    
9. Selecione **Definir como padrão**.
    
10. Para idiomas que deseja remover:
    
    a. Selecione o idioma que deseja remover.
    
    b. Selecione **Remover**.
    
11. Inicie um prompt de comandos com privilégios elevados.
    
12. Execute o seguinte comando: 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. Reinicie o sistema.
    
Seu idioma desejado agora é aplicado ao console Salas do Microsoft Teams.
## <a name="initial-set-up-of-the-console"></a>Configuração inicial do console
<a name="Initial"> </a>

Depois Windows for instalado, o aplicativo Salas do Microsoft Teams entrará em seu processo inicial de Instalação.
  
1. A tela Conta de Usuário é exibida. Insira o endereço de entrada da conta de recurso do Microsoft Exchange (no formato user@domain) da conta de sala a ser usada com o console.
    
2. Digite a senha para a conta da sala e digite-a novamente para verificar.
   
3. Selecione o modo de reunião com suporte - somente Microsoft Teams, Skype for Business Somente ou uma das duas opções de modo misto. Se necessário, habilita a Autenticação Moderna.

4. Click **Next**.
    
5. Se usar Skype for Business e se o domínio SIP do Skype for Business for diferente do domínio Exchange do usuário, de definir o FQDN para o Skype for Business Server na seção Avançado. Se você não estiver usando Skype for Business ou o domínio SIP corresponde ao domínio Exchange, deixe esta seção em branco.
6. Click **Next**.
    
7. Clique em **Concluir**.
    
O Salas do Microsoft Teams app deve entrar no Microsoft Teams ou Skype for Business Server com as credenciais inseridas acima e também deve começar a sincronizar seu calendário com Exchange usando essas mesmas credenciais. Para obter detalhes sobre como Salas do Teams, consulte a Salas do Microsoft Teams [ajuda](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).
  
> [!IMPORTANT]
> Salas do Microsoft Teams depende da presença de hardware de console certificado. Mesmo uma imagem criada corretamente contendo o aplicativo de console Salas do Microsoft Teams não será inicializada após o procedimento de instalação inicial, a menos que o hardware do console seja detectado. Para Surface Pro soluções baseadas em Surface Pro, o Surface Pro deve estar conectado ao hardware de encaixe que acompanha para passar essa verificação.
  
> [!NOTE]
> Alguns usuários de idiomas que não são do inglês podem precisar de um teclado físico conectado ao console durante a configuração inicial, caso os símbolos não sejam suportados no teclado por toque.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>Instalar um certificado ca privado no console
<a name="Certs"> </a>
> [!NOTE]
> O seguinte só se aplica se a conexão Salas do Teams a Skype for Business.

Salas do Microsoft Teams precisa confiar nos certificados usados pelos servidores aos que ele se conecta. Em um caso em que a Autoridade de Certificação é privada, por exemplo, uma implantação local com o Active Directory e a Autoridade de Certificação Windows, você pode adicionar o certificado Salas do Microsoft Teams de várias maneiras:
  
- Você pode ingressar o console no Active Directory e isso adicionará automaticamente os certificados necessários, uma vez que a Autoridade de Certificação é publicada no Active Directory (opção de implantação normal).
    
- Você pode instalar o certificado manualmente após o processo de geração de imagens. Antes de fazer isso, você deve concluir [a configuração inicial do console](console.md#Initial).
    
### <a name="to-manually-install-the-certificate"></a>Para instalar o certificado manualmente 

1. Baixe o certificado de autoridade de certificação para seu computador e salve-o em "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".
    
2. Coloque o console no modo de administração (consulte [Admin mode and device management](rooms-operations.md#AdminMode)).
    
3. Execute o seguinte comando:
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Ingressar em um domínio do Active Directory (Opcional)
<a name="Certs"> </a>

Você pode ingressar Salas do Microsoft Teams seu domínio. Salas do Microsoft Teams deve ser colocado em uma OU separada de suas estações de trabalho do computador porque muitas políticas de estação de trabalho não são compatíveis com Salas do Microsoft Teams. Um exemplo comum são políticas de aplicação de senha que impedirão Salas do Microsoft Teams iniciar automaticamente. Para obter informações sobre o gerenciamento de configurações de GPO, consulte [Manage Salas do Microsoft Teams](rooms-operations.md).
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>Para ingressar Salas do Microsoft Teams a um domínio

1. Entre no console da conta de administrador (consulte [Admin mode and device management](rooms-operations.md#AdminMode)).
    
2. Inicie o comando em um prompt de comandos com privilégios elevados do Powershell.
    
3. Digite o seguinte comando no Powershell:
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

Por exemplo, se seu domínio totalmente qualificado for redmond.corp.microsoft.com e você quiser que seus consoles de Salas do Microsoft Teams sejam em uma OU "Salas do Microsoft Teams" que seja filho de uma OU "Resources", o comando será:
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 Se você quiser renomear o computador ao jun-lo a um domínio, use o sinalizador -NewName seguido pelo novo nome do computador.
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Salas do Microsoft Teams lista de verificação de implantação
<a name="Checklist"> </a>

Use a seguinte lista de verificação ao fazer uma verificação final de que o console e todos os periféricos estão totalmente configurados:
  
**Configurações do aplicativo**

|Concluído |Verificar |
|:-----:|:-----|
|☐   |Nome da conta de sala e telefone # (se PSTN habilitado) são exibidos corretamente   |
|☐   |O nome do computador Windows está definido corretamente (útil para administração remota)   |
|☐   |A senha da conta do administrador foi definida e verificada   |
|☐   |Todas as atualizações de firmware foram aplicadas   |
   
**Periféricos de áudio/vídeo**

|Concluído |Verificar |
|:-----:|:-----|
|☐   |A versão do firmware do periférico da câmera está correta (se aplicável)   |
|☐   |Câmera funcional e posicionada de forma ideal   |
|☐   |Configurações para o Dispositivo de Reprodução Padrão e o Dispositivo de Comunicações Padrão definidas para o periférico de áudio desejado   |
|☐   |Configurações para Registrar o Dispositivo de Comunicação Padrão definidas para o periférico de áudio desejado   |
|☐   |A versão do firmware do periférico de áudio está correta (se aplicável)   |
|☐   |Dispositivo de entrada de áudio funcional e posicionado corretamente   |
|☐   |Dispositivo de saída de áudio funcional e posicionado corretamente   |

**Console**

|Concluído |Verificar |
|:-----:|:-----|
|☐   |Os cabos estão presos e não estão dobrados   |
|☐   |Ingestão de áudio via HDMI funcional   |
|☐   |Ingestão de vídeo via HDMI funcional   |
|☐   |Console pode girar livremente   |



   
## <a name="see-also"></a>Confira também
<a name="Checklist"> </a>

[Planejar as Salas do Microsoft Teams](rooms-plan.md)
  
[Implantar Salas do Microsoft Teams](rooms-deploy.md)
  
[Configurar um console de Salas do Microsoft Teams](console.md)
  
[Gerenciar Salas do Microsoft Teams](rooms-manage.md)
