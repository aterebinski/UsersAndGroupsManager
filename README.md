# UsersAndGroupsManager
Gotowy szkielet apliakcji za wbudowanyą obsługą rejestracji, logowania, potwierdzenia maila, odzyskiwania hasła, obsługi użytkowników i ról.

Obsługa userów i grup na podstawie tutoriala:
https://codewithmukesh.com/blog/user-management-in-aspnet-core-mvc/

Konfiguracja email za pomoca usługi SendGrida na podstawie tutoriala:
https://docs.microsoft.com/pl-pl/aspnet/core/security/authentication/accconfirm?view=aspnetcore-5.0&tabs=visual-studio

W celu poprawnej konfiguracji należy zarejestrować się na portalu sendgrid, potwierdzić swój email, uzupełnić dane sendera, wygenerować swój klucz APIKey. (Settings -> APIKey).
W katalogu z projektem (csproj) należy wykonać komendę:
dotnet user-secrets set SendGridKey <SG.key>
, gdzie <SG.key> to klucz APIKey wygenerowany wcześniej w portalu sendgrid.

W programie w pliku services/EmailSender.cs należy w miejscu:
                // Please cnange Email address according to SendGrid Sender
                From = new EmailAddress("sender@gmail.com", "Password Recovery"),
dodać email zgodny z emailem sendera w sendgrid.


Aby zamiast usługi SendGrid użyć standardowego konta pocztowego do potwierdzania maili, należy skorzystac z tutoriali:
https://code-maze.com/email-confirmation-aspnet-core-identity/
https://www.yogihosting.com/aspnet-core-identity-email-confirmation/
