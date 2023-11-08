# OCTANET-NOVEMBER
#html code
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8">
	<meta name="viewport" content="width=device-width, initial-scale=1">
	<title>Hamburger Menu</title>
	<link rel="stylesheet" type="text/css" href="style2.css">
	<link rel="stylesheet" href="https://unpkg.com/boxicons@2.1.4/css/boxicons.min.css">
</head>
<body>
	<header class="header">
		<a href="#" class="logo">HAMBURGER MENU</a>

		<input type="checkbox" id="check">
		<label for="check" class="icons">
			<i class="bx bx-menu" id="menu-icon"></i>
			<i class="bx bx-x" id="close-icon"></i>
		</label>

		<nav class="navbar">
			<a href="#" style="--i:0;">Home</a>
			<a href="#" style="--i:1;">About</a>
			<a href="#" style="--i:2;">Gallery</a>
			<a href="#" style="--i:3;">Services</a>
			<a href="#" style="--i:4;">Contact</a>
		</nav>
	</header>

</body>
</html>
#css code
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800;900&display=swap");
*
{
	margin: 0;
	padding: 0;
	box-sizing: border-box;
	font-family: "Poppins" , sans-serif;
}

body
{
	min-height: 100vh;
	background: url('https://burst.shopifycdn.com/photos/fog-on-dark-waters-edge.jpg?width=1000&format=pjpg&exif=0&iptc=0') no-repeat;
	background-size: cover;
	background-position: center;
}

.header
{
	position: fixed;
	top: 0;
	left: 0;
	width: 100%;
	padding: 1.3rem 10%;
	display: flex;
	justify-content: space-between;
	align-items: center;
	z-index: 100;
}

.header::before
{
	content: '';
	position: absolute;
	top: 0;
left: 0;
	width: 100%;
	height: 100%;
	background: rgba(0, 0, 0, .1);
	backdrop-filter: blur(50px);
	z-index: -1;
}

.header::after 
{
	content: '';
	position: absolute;
	top: 0;
	left: -100%;
	width: 100%;
	height: 100%;
	background: linear-gradient(90deg, transparent, rgba(255,255,255,.4), transparent);
	transition: .5s;
}

.header:hover::after
{
	left: 100%;
}

.logo
{
	font-size: 2rem;
	color: #fff;
	text-decoration: none;
	font-weight: 700;
}

.navbar a 
{
	font-size: 1.15rem;
	color: #fff;
	text-decoration: none;
	font-weight: 500;
	margin-left: 2.5rem;
}

#check
{
	display: none;
}

.icons
{
	position: absolute;
	right: 5%;
font-size: 2.8rem;
	color: #fff;
	cursor: pointer;
	display: none;
}

@media(max-width: 992px)
{
	.header
	{
		padding: 1.3rem 5%;
	}
}

@media(max-width: 768px)
{
	.icons
	{
		display: inline-flex;
	}

	#check:checked~.icons #menu-icon
	{
		display: none;
	}

	.icons #close-icon
	{
		display: none;
	}
	#check:checked~.icons #close-icon
	{
		display: block;
	}

	.navbar
	{
		position: absolute;
		top: 100%;
left: 0;
		width: 100%;
		height: 0;
		background: rgba(0, 0, 0, .1);
		backdrop-filter: blur(50px);
		box-shadow: 0.5rem 1rem rgba(0, 0, 0, .1);
		overflow: hidden;
		transition: .3s ease;
	}

	#check:checked~.navbar
	{
		height: 17.7rem;
	}

	.navbar a 
	{
		display: block;
		font-size: 1.1rem;
		margin: 1.5rem 0;
		text-align: center;
		transform: translateY(-50px);
		opacity: 0;
		transition: .3s ease;
	}
	#check:checked~.navbar a
	{
		transform: translateY(0);
		opacity: 1;
		transition-delay: calc(.15s * var(--i));
	}

}
