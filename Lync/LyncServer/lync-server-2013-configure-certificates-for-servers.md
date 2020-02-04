---
title: 'Lync Server 2013: Configurar certificados para servidores'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for servers
ms:assetid: e12e59b5-a146-4859-86ec-cabfc198c7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398995(v=OCS.15)
ms:contentKeyID: 48185531
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 303724fa705fa94e9bbacacb4764bba7b918c460
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739371"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-servers-in-lync-server-2013"></a>Configurar certificados para servidores no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-03-17_

Para concluir esse procedimento com êxito, você deve estar conectado como um usuário que é membro do grupo RTCUniversalServerAdmins ou ter as permissões corretas delegadas. Para obter detalhes sobre como delegar permissões, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md). Dependendo da sua organização e dos requisitos para solicitar certificados, você pode exigir outras associações de grupo. Consulte o grupo que gerencia sua autoridade de certificação (PKI) da infraestrutura de chave pública (PKI).

<div>


> [!NOTE]  
> O Lync Server 2013 inclui suporte para o pacote SHA-2 (SHA-2 usa os comprimentos de resumo dos bits do 224, 256, 384 ou 512) do hash de resumo e dos algoritmos de assinatura para conexões de clientes que executam o Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista ou Sistemas operacionais Windows XP, além do Lync Phone Edition. Para suportar o acesso externo usando o pacote do SHA-2, o certificado externo é emitido por uma AC pública que também pode emitir um certificado com a mesma extensão de disco.



</div>

<div>


> [!WARNING]  
> A seleção do resumo do hash e do algoritmo de assinatura dependerá do cliente e dos servidores que utilizarão o certificado, e de outros computadores e dispositivos que os clientes e servidores comunicarão a quem também deve saber como usar os algoritmos usados no certificado. Para obter informações sobre quais tamanhos de resumo são compatíveis com o sistema operacional e alguns aplicativos cliente,<A href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</A>consulte.



</div>

Cada servidor de front-end ou servidor Standard Edition requer até quatro certificados: o certificado oAuthTokenIssuer, um certificado padrão, um certificado interno da Web e um certificado externo da Web. No entanto, é possível solicitar e atribuir um único certificado padrão com entradas de nome alternativo de assunto apropriado, bem como o certificado oAuthTokenIssuer. Para obter detalhes sobre os requisitos de certificado, consulte [requisitos de certificado para servidores internos no Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md). Para obter detalhes sobre como solicitar, atribuir e instalar o certificado oAuthTokenIssuer, consulte [Gerenciando a autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

Use o procedimento a seguir para solicitar, atribuir e instalar os certificados do servidor Standard Edition ou do servidor front-end. Repita o procedimento para cada servidor front-end.

<div>


> [!IMPORTANT]  
> O procedimento a seguir descreve como configurar certificados de uma PKI corporativa interna implantada pela sua organização e com o processamento de solicitações offline. Para obter informações sobre como obter certificados de uma autoridade de certificação pública, consulte <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">requisitos de certificado para servidores internos no Lync Server 2013</A> na documentação de planejamento. Além disso, esse procedimento descreve como solicitar, atribuir e instalar certificados durante a configuração do servidor front-end. Se você solicitou certificados antecipadamente, conforme descrito na seção <A href="lync-server-2013-request-certificates-in-advance-optional.md">solicitar certificados na seção Avançado (opcional) do Lync Server 2013</A> desta documentação de implantação, ou se não usar uma PKI corporativa interna implantada em sua organização para obter certificados, você deve modificar esse procedimento conforme apropriado.



</div>

<div>

## <a name="to-configure-certificates-for-a-front-end-server"></a>Para configurar certificados para um servidor front-end

1.  No assistente de implantação do Lync Server, clique em **executar** ao lado da **etapa 3: solicitar, instalar ou atribuir certificados**.

2.  Na página **Assistente de Certificados**, clique em **Solicitar**.

3.  Na página **solicitação de certificado** , clique em **Avançar**.

4.  Na página **Solicitações Atrasadas ou Imediatas**, é possível aceitar a opção padrão **Enviar a solicitação imediatamente para uma autoridade de certificação online** clicando em **Avançar**. A AC interna com inscrição online automática precisa estar disponível se você selecionar essa opção. Se você escolher a opção para atrasar a solicitação, receberá uma solicitação para fornecer um nome e local para salvar o arquivo de solicitação do certificado. A solicitação de certificado precisa ser apresentada a processada por uma AC dentro de sua organização ou por uma AC pública. Em seguida, será necessário importar a resposta do certificado e atribuí-la à função de certificado apropriada.

5.  Na página **escolher uma CA (autoridade** de certificação), selecione a opção **selecionar uma autoridade de certificação na lista detectada em seu ambiente** e, em seguida, selecione uma autoridade de certificação conhecida (por meio de registro nos serviços de domínio Active Directory) na lista. Como alternativa, selecione a opção **Especificar outra autoridade de certificação**, digite o nome de outra AC na caixa e clique em **Avançar**.

6.  Na página **Conta da Autoridade de Certificação**, você deve informar as credenciais para solicitar e processar a solicitação de certificado na AC. Você deve determinar com antecedência se um nome de usuário e uma senha são necessários para solicitar um certificado. O administrador da sua CA terá as informações necessárias e poderá ter que ajudá-lo nesta etapa. Se precisar fornecer credenciais alternativas, marque a caixa de seleção, digite um nome de usuário e uma senha nas caixas de texto e clique em **Avançar**.

7.  Na página **Especificar Modelo de Certificado Alternativo**, para usar o modelo de Servidor da web padrão, clique em **Avançar**.
    
    <div>
    

    > [!NOTE]  
    > Se sua organização tiver criado um modelo para ser usado como uma alternativa para o modelo de AC padrão do Servidor da web, marque a caixa de seleção, e digite o nome do modelo alternativo. Você precisará do nome do modelo, conforme definido pelo administrador de AC.

    
    </div>

8.  Na página **configurações de nome e segurança** , especifique um **nome amigável** que deve permitir a identificação do certificado e da finalidade. Se você deixá-lo em branco, um nome será gerado automaticamente. Defina o **comprimento do bit** da chave ou aceite o padrão de 2048 bits. Selecione a **chave privada do certificado como exportável** se você determinar que o certificado e a chave privada precisam ser movidos ou copiados para outros sistemas e clique em **Avançar**.
    
    <div>
    

    > [!NOTE]  
    > O Lync Server 2013 tem requisitos mínimos para uma chave privada exportável. Um exemplo disso são os Servidores de Borda em um pool, onde o Serviço de Autenticação de Media Relay usa cópias do certificado, em vez de certificados individuais para cada instância no pool.

    
    </div>

9.  Na página **Informações da Organização**, forneça, opcionalmente, as informações da organização e clique em **Avançar**.

10. Na página **Informações Geográficas**, forneça, opcionalmente, informações geográficas e clique em **Avançar**.

11. Na página **Nome da Entidade/Nomes Alternativos da Entidade**, revise os nomes alternativos da entidade que serão adicionados e clique em **Avançar**.

12. Na página **Configuração do Domínio SIP**, selecione o **Domínio SIP** e clique em **Avançar**.

13. Na página **Configurar Nomes Alternativos da Entidade Adicionais**, adicione quaisquer nomes alternativos da entidade adicionais necessários, incluindo qualquer um que possa ser exigido para domínios SIP adicionais no futuro, e clique em **Avançar**.

14. Na página **Resumo da Solicitação de Certificado**, revise as informações no resumo. Se as informações estiverem corretas, clique em **Avançar**. Se você precisar corrigir ou modificar uma configuração, clique em **Voltar** para a página apropriada a fim de fazer a correção ou modificação.

15. Na página **Executando Comandos**, clique em **Avançar**.

16. On the **Online Certificate Request Status** page, review the information returned. You should note that the certificate was issued and installed into the local certificate store. Se for reportado como tendo sido emitido e instalado, mas não for válido, verifique se o certificado raiz da CA foi instalado no repositório da CA raiz confiável do servidor. Refer to your CA documentation on how to retrieve a Trusted Root CA certificate. If you need to view the retrieved certificate, click **View Certificate Details**. Por padrão, a caixa de seleção para **atribuir o certificado a usos de certificado do Lync Server** está marcada. If you want to manually assign the certificate, clear the check box, and then click **Finish**.

17. Se você desmarcou a caixa de seleção para **atribuir o certificado aos usos de certificado do Lync Server** na página anterior, você será apresentado à página **atribuição de certificado** . Click **Next**.

18. Na página **Repositório de Certificados**, selecione o certificado que você solicitou. Se você quiser ver o certificado, clique em **Exibir Detalhes do Certificado** e clique em **Avançar** para continuar.
    
    <div>
    

    > [!NOTE]  
    > Se a página <STRONG>status da solicitação de certificado online</STRONG> relatou um problema com o certificado, como o certificado que não é válido, a exibição do certificado real pode ajudar a solucionar o problema. Dois problemas específicos que podem fazer com que um certificado seja inválido são a ausência o certificado AC raiz confiável, mencionada anteriormente, e a ausência de uma chave privada associada ao certificado. Consulte a documentação da AC para resolver esses dois problemas.

    
    </div>

19. Na página **Resumo de Atribuição de Certificado**, examine as informações apresentadas a fim de assegurar que esse certificado deve ser atribuído e clique em **Avançar**.

20. Na página **Executando Comandos**, revise a saída do comando. Clique em **Exibir Log** se você quiser revisar o processo de atribuição ou se houver um erro ou aviso. Após a conclusão da revisão, clique em **Concluir**.

21. Na página do **Assistente de certificado** , verifique se o **status** do certificado é "atribuído" e clique em **Fechar**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Requisitos de infraestrutura de certificado para o Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

