---
title: Configurar um console de salas de equipes da Microsoft
ms.author: v-lanac
author: lanachin
ms.reviewer: Travis-Snoozy
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: Este artigo descreve como configurar o console de salas de equipes da Microsoft e seus periféricos.
ms.openlocfilehash: 644006b3fe5a26af6c32830902ec138f953464c8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33916562"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a>Configurar um console de salas de equipes da Microsoft

Este artigo descreve como configurar o console de salas de equipes da Microsoft e seus periféricos.
  
Você só deve executar estas etapas se o necessário Teams da Microsoft ou Skype para contas de negócios e do Exchange já foram criado e testado, conforme descrito em [Implantar salas de equipes da Microsoft](room-systems-v2.md). Você precisará de hardware e software descritos em [requisitos de salas de equipes da Microsoft](requirements.md). Este tópico inclui as seguintes seções:
  
- [Preparar a mídia de instalação](console.md#Prep_Media)
- [Instale um certificado de autoridade de certificação privado no console do](console.md#Certs)
- [Instalar o Windows 10 e o aplicativo de console de salas de equipes da Microsoft](console.md#Reimage)
- [Conjunto inicial backup do console](console.md#Initial)
- [Lista de verificação de implantação de salas de equipes da Microsoft](console.md#Checklist)

> [!NOTE]
> Salas de equipes da Microsoft funcionará somente em um Microsoft Teams ou o Skype configuradas adequadamente para onde as contas de dispositivo estão configuradas corretamente conforme descrito em [Implantar o Microsoft equipes salas](room-systems-v2.md)do ambiente de negócios.
  
## <a name="prepare-the-installation-media"></a>Preparar a mídia de instalação
<a name="Prep_Media"> </a>

Instalar o aplicativo de console do Microsoft equipes salas requer um dispositivo de armazenamento USB com pelo menos 32GB de capacidade. Não deve haver nenhum outro arquivo no dispositivo. todos os arquivos existentes no armazenamento USB será perdidos.
  
> [!NOTE]
> Falha ao criar sua mídia de instalação do Microsoft equipes salas de acordo com estas instruções provavelmente resultará em um comportamento inesperado.

> [!NOTE]
> O processo abaixo é para a criação de mídia de instalação para novos dispositivos de salas de equipes da Microsoft de imagem. Dispositivos existentes, por padrão, atualizam automaticamente do Windows Update e o repositório do Windows.
  
1. Baixe o [script CreateSrsMedia.ps1](https://go.microsoft.com/fwlink/?linkid=867842).
2. Execute o script CreateSrsMedia.ps1 de um prompt com privilégios elevados em um computador Windows 10.
3. Siga as instruções do script para criar um disco de instalação do Microsoft equipes salas USB.


> [!TIP]
> Sempre que o script CreateSrsMedia.ps1 é iniciado, a saída na tela incluirá o nome de um arquivo de log ou a transcrição da sessão. Se houver problemas com a execução do script, certifique-se tiver uma cópia dessa transcrição disponível ao solicitar suporte. 

O script CreateSrsMedia.ps1 automatiza as seguintes tarefas:

1. Baixe o instalador MSI mais recente para salas de equipes da Microsoft.
2. Determine a compilação do Windows que o usuário deve fornecer. As versões liberadas recentemente podem ou não podem ser testadas e suportadas para uso com dispositivos de salas de equipes da Microsoft.
3. Baixe os componentes de suportados necessários.
4. Monte os componentes necessários na mídia de instalação.

É necessária uma versão específica do Windows 10 e esta versão só está disponível para clientes de licenciamento de volume.  Você pode obter uma cópia do [Centro de atendimento de licenciamento por Volume](https://www.microsoft.com/Licensing/servicecenter/).

Quando terminar, remova o disco USB do computador e prossiga para [instalar o Windows 10 e as salas de equipes da Microsoft app do console](console.md#Reimage).

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Instalar o Windows 10 e o aplicativo de console de salas de equipes da Microsoft
<a name="Reimage"> </a>

Agora, você precisa aplicar a mídia de instalação que você criou. O dispositivo de destino será executado como um dispositivo e o usuário padrão será definido como executar somente o aplicativo de console do Microsoft equipes salas.

1. Se o dispositivo de destino será instalado em um (por exemplo, um Surface Pro) de encaixe, desconecte-o do encaixe.

2. Certifique-se de que o dispositivo de destino não está conectado à rede.

3. Certifique-se de que o dispositivo de destino está conectado à alimentação AC.

4. Conecte seu disco de instalação do USB no dispositivo de destino.

5. Inicialize o disco de instalação do USB. Consulte as instruções do fabricante. Se seu dispositivo de destino for um Surface Pro, use as seguintes etapas para inicializar o disco de instalação do USB:

    a. Pressione e continue armazenar o volume (-) botão pressionado.

    b. Pressione e solte o botão de energia.

    c. Depois que a instalação do Windows for inicializada, solte o botão de abaixar o volume (-).

8. O sistema será desligado depois que a instalação for concluída.
    
Depois que o sistema foi desligado, é seguro remover o disco de instalação do USB. Neste ponto, você pode colocar o dispositivo de destino no seu encaixe (se estiver usando um produto com base em encaixe), anexar os periféricos necessários para a sala de reunião e conectar à rede. Consulte as instruções do fabricante.
  
### <a name="selecting-a-language"></a>Selecionar um idioma 

Em atualização do criador, você precisará usar o script de ApplyCurrentRegionAndLanguage.ps1 em cenários onde a seleção de idioma implícita não fornecer ao usuário com a linguagem de aplicativos real querem (por exemplo, eles querem que o aplicativo de console surgir em francês, mas ele está chegando em inglês).
  
> [!NOTE]
> As instruções a seguir funcionam apenas para consoles criados usando Update do criador do Windows. Sistemas herdados/no mercado que não foram configurados usando mídia com o novo sistema de provisionamento não será capazes de usar estas instruções, mas também deve não sofrem o problema inicial que requer intervenção este manual (edição de aniversário permitam que você escolha sua idioma App explicitamente como parte da instalação).
  
### <a name="to-apply-your-desired-language"></a>Para aplicar o idioma desejado

1. Mude para o modo de Administrador.
    
2. Selecione o menu Iniciar.
    
3. Selecione o ícone de engrenagem para iniciar o aplicativo de **Configurações**.
    
4. Selecione **tempo &amp; idioma**.
    
5. Selecione **região &amp; idioma**.
    
6. Selecione **Adicionar um idioma**.
    
7. Selecione o idioma que deseja adicionar.
    
8. Selecione o idioma que você acabou de adicionar à lista de "Idiomas".
    
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
    
O idioma desejado agora é aplicado no console de salas de equipes da Microsoft.
## <a name="initial-set-up-of-the-console"></a>Conjunto inicial backup do console
<a name="Initial"> </a>

Após a instalação do Windows, o aplicativo de console do Microsoft equipes salas entrará em seu processo de instalação inicial, quando ele é iniciado próximo ou se a opção /reboot foi escolhida.
  
1. A tela Conta de Usuário é exibida. Insira o Skype endereço de entrada (no formato user@domain) da conta a ser usado com o console de sala.
    
2. Digite a senha para a conta da sala e digite-a novamente para verificar.
    
3. Em "Configurar domínio", defina o FQDN para o Skype para Business Server. Se o Skype para o domínio SIP de negócios for diferente do domínio do Exchange do usuário, insira o domínio do Exchange neste campo.
    
4. Click **Next**.
    
5. Selecione os dispositivos indicados na tela recursos e clique em **Avançar**. O padrão é ter o compartilhamento automático de tela definido como Ativado e Ocultar os nomes da reunião definido como Desativado. Os dispositivos para selecionar são:
    
   - Microfone para conferência: o microfone padrão para a sala de conferência.
    
   - Alto-falante para conferência: o alto-falante padrão para conferência  
    
   - Alto-falante padrão: o alto-falante usado para áudio da ingestão HDMI.
    
     Cada item tem um menu suspenso de opção para seleção. Você deve fazer uma seleção para cada dispositivo.
    
6. Clique em **Concluir**.
    
O aplicativo de console do Microsoft equipes salas deve iniciar imediatamente entrando no Skype para Business Server com as credenciais inseridas acima e também deve começar a sincronizar seu calendário com Exchange usando as mesmas credenciais. Para obter detalhes sobre como usar o aplicativo de console, consulte a [Ajuda do Microsoft equipes salas](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).
  
> [!IMPORTANT]
> Salas de equipes da Microsoft depende da presença de hardware do console certificados. Mesmo uma imagem criada corretamente que contém o aplicativo de console do Microsoft equipes salas não inicializa passado o procedimento de instalação inicial, a menos que o hardware do console for detectado. Para obter soluções Surface Pro com base, o Surface Pro deve estar conectada a seu hardware de encaixe acompanha para passar essa verificação.
  
> [!NOTE]
> Alguns usuários de idioma diferente do inglês, talvez seja necessário um teclado físico conectado ao console durante a configuração inicial que símbolos não são suportados no teclado de toque.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>Instale um certificado de autoridade de certificação privado no console do
<a name="Certs"> </a>

O console de salas de equipes da Microsoft deve confiar nos certificados usados pelos servidores a que conecta-se. No O365, isso é feito automaticamente, pois esses servidores usam Autoridades de Certificação públicas e o Windows 10 confia nelas automaticamente. No caso em que a autoridade de certificação é particular, por exemplo, uma implantação de local com o Active Directory e a autoridade de certificação do Windows, você pode adicionar o certificado no console de salas de equipes da Microsoft de duas maneiras:
  
- Ingresse o console do Active Directory e que adicionará automaticamente os certificados necessários dado da autoridade de certificação é publicado no Active Directory (opção de implantação normal).
    
- Você pode instalar o certificado manualmente após o processo de geração de imagens. Antes de fazer isso, você deve concluir a [Configurar as iniciais do console](console.md#Initial).
    
### <a name="to-manually-install-the-certificate"></a>Para instalar o certificado manualmente 

1. Baixe o certificado de autoridade de certificação para seu computador e salve-o em "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".
    
2. Coloque o console no modo de administração (consulte [gerenciamento de dispositivo e modo de Admin](room-systems-v2-operations.md#AdminMode)).
    
3. Execute o seguinte comando:
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Ingressar em um domínio do Active Directory (opcional)
<a name="Certs"> </a>

Você pode ingressar consoles de salas de equipes da Microsoft para o seu domínio. Consoles de salas de equipes da Microsoft devem ser colocados em uma UO separada estações de trabalho do seu PC, porque muitos políticas de estação de trabalho não são compatíveis com Microsoft equipes salas. Um exemplo comum são as diretivas de aplicação da senha que evitam a salas de equipes da Microsoft seja iniciado automaticamente. Para obter informações sobre o gerenciamento de configurações do GPO, consulte [Manage Rooms de equipes da Microsoft](room-systems-v2-operations.md).
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>Para ingressar em salas de equipes da Microsoft a um domínio

1. Sinal de login no console do que o administrador da conta (consulte [gerenciamento de dispositivo e modo de Admin](room-systems-v2-operations.md#AdminMode)).
    
2. Inicie o comando em um prompt de comandos com privilégios elevados do Powershell.
    
3. Digite o seguinte comando no Powershell:
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

Por exemplo, se o seu domínio totalmente qualificado for redmond.corp.microsoft.com e você quiser que seus consoles de salas de equipes da Microsoft para estar em uma unidade Organizacional "Salas de equipes da Microsoft" que é um filho de uma unidade Organizacional "recursos", o comando será:
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 Se você gostaria de renomear o computador ao ingressarem-lo a um domínio, use o sinalizador - NewName seguido pelo nome do novo do computador.
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Lista de verificação de implantação de salas de equipes da Microsoft
<a name="Checklist"> </a>

Use a seguinte lista de verificação enquanto efetua uma verificação final se o console e todos os seus periféricos totalmente estão configurados:
  
**Configurações do aplicativo**

|||
|:-----|:-----|
|☐  <br/> |O Nome e o número de telefone da conta da sala (se PSTN estiver habilitado) são exibidos corretamente na parte superior direita da tela do console  <br/> |
|☐  <br/> |O nome do computador Windows está definido corretamente (útil para administração remota)  <br/> |
|☐  <br/> |A senha da conta do administrador foi definida e verificada  <br/> |
|☐  <br/> |Todas as atualizações de firmware tiverem sido aplicadas.  <br/> |
   
**Periféricos de áudio/vídeo**

|||
|:-----|:-----|
|☐  <br/> |A versão do firmware do periférico da câmera está correta (se aplicável)  <br/> |
|☐  <br/> |Câmera funcional e forma ideal posicionada  <br/> |
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

[Planejar para salas de equipes da Microsoft](skype-room-systems-v2-0.md)
  
[Implantar salas de equipes da Microsoft](room-systems-v2.md)
  
[Configurar um console de salas de equipes da Microsoft](console.md)
  
[Gerenciar Salas do Microsoft Teams](skype-room-systems-v2.md)
