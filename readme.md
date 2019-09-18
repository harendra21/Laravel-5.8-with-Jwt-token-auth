

## Laravel 5.8 with Jwt token auth

1. git clone
2. cd project-folder
3. composer update
4. edit .env file to setup database
5. php artisan migrate
6. php artisan migreate --seed
7. php artisan serve

### Login
	URL : http://localhost:8000/api/login
	Method : POST
	Header : Content-Type : application/x-www-form-urlencoded
	Body : 	email : admin@admin.com
			password : admin

	Output :
			{
				"token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC9sb2NhbGhvc3Q6ODAwMFwvYXBpXC9sb2dpbiIsImlhdCI6MTU2ODc5MjQ5OSwiZXhwIjoxNTY4Nzk2MDk5LCJuYmYiOjE1Njg3OTI0OTksImp0aSI6Imo4VmZrZVUwYlhWSGdJNmkiLCJzdWIiOjEsInBydiI6Ijg3ZTBhZjFlZjlmZDE1ODEyZmRlYzk3MTUzYTE0ZTBiMDQ3NTQ2YWEifQ.Ut3eYZjz6fikXvbrViDmc8y0gxK7gBf9OvgkoWdrgYQ",
				"type": "bearer",
				"expires": 3600
			}

	Copy this token

### Get list of users
	URL : http://localhost:8000/api/users
	Method : GET
	Header : Authorization : Bearer your-token

	Output :
			{
				"id": 1,
				"name": "Administrator",
				"email": "admin@admin.com",
				"email_verified_at": null,
				"created_at": "2019-09-18 07:18:55",
				"updated_at": "2019-09-18 07:18:55"
			}