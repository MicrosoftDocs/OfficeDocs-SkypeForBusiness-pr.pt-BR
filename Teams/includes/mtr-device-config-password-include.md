
Como qualquer conta do Microsoft 365, a senha de uma conta de recurso recém-criada é definida para expirar automaticamente após um período de tempo. No entanto, se a senha da conta de recurso expirar, o Salas do Teams em que ela está conectada não poderá entrar novamente na data de expiração. 

Para evitar a necessidade de redefinir a senha da conta de recurso e, em seguida, fazer logon em cada dispositivo Salas do Teams novamente, você pode desativar a expiração de senha para a conta.
  
> [!NOTE]
> A **configuração de senha nunca expira** é um requisito para dispositivos compartilhados do Microsoft Teams. Se suas regras de domínio proibirem senhas que não expiram, você precisará criar uma exceção para cada conta de recurso de dispositivo do Teams.

Siga as etapas em uma das seguintes guias para desativar a expiração da senha:

#### <a name="azure-active-directory-20"></a>[**Azure Active Directory 2.0**](#tab/azure-active-directory2-password/)

Primeiro, conecte-se ao Active Directory PowerShell:

```PowerShell
   Connect-AzureAD
```

Em seguida, consulte [Definir uma senha para nunca expirar](/microsoft-365/admin/add-users/set-password-to-never-expire#set-a-password-to-never-expire).

Este exemplo define a senha para a conta ConferenceRoom01@contoso.com nunca expirar.

```PowerShell
Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -PasswordPolicies DisablePasswordExpiration
```

#### <a name="azure-active-directory-10"></a>[**Azure Active Directory 1.0**](#tab/azure-active-directory1-password/)

 1. Conecte-se ao MSOnline PowerShell:

       ```PowerShell
       Connect-MsolService
       ```

       Para obter detalhes sobre o Active Directory, [consulte O Azure Active Directory (MSOnline)](/powershell/azure/active-directory/overview?view=azureadps-1.0&preserve-view=true).

2. Defina a senha para nunca expirar usando a seguinte sintaxe:

    ```PowerShell
    Set-MsolUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    Este exemplo define a senha para a conta ConferenceRoom01@contoso.com nunca expirar.

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```

#### <a name="active-directory-on-premises"></a>[**Active Directory (local)**](#tab/active-directory1-password/)

1. Conecte-se ao Active Directory PowerShell:

    ```PowerShell
       Import-Module ActiveDirectory
    ```
    
    Para obter detalhes sobre o Active Directory PowerShell, consulte [ActiveDirectory](/powershell/module/activedirectory).

2. Defina a senha para nunca expirar usando a seguinte sintaxe:

    ```PowerShell
    Set-ADUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    Este exemplo define a senha para a conta ConferenceRoom01@contoso.com nunca expirar.

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---